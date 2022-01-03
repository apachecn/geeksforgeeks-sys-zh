# 在 C++中实现竞争条件

> 原文:[https://www . geeksforgeeks . org/impering-race-condition-in-c/](https://www.geeksforgeeks.org/implementing-race-condition-in-c/)

**先决条件–**[种族条件弱点](https://www.geeksforgeeks.org/race-condition-vulnerability/)

当执行中的两个并发线程以一种方式访问共享资源时，它会根据线程或进程的定时无意中产生不同的结果，这就产生了**竞争条件**。

简单地说:
如果我们的特权程序(具有提升的访问控制的应用程序)也有一个带有竞争条件漏洞的代码块，那么攻击者可以通过运行能够与我们的特权程序“竞争”的并行进程来利用这一点。如果他们攻击的意图是改变其实际的预期行为，那么这可能会在我们的程序中造成竞争条件。

**示例:**

```
/* A Vulnerable Program */
int main() {
    char * fn = "/tmp/XYZ";
    char buffer[60];
    FILE *fp;
    /* get user input */
    scanf("%50s", buffer );

    if(!access(fn, W_OK)){
        fp = fopen(fn, "a+");
        fwrite("\n", sizeof(char), 1, fp);
        fwrite(buffer, sizeof(char), strlen(buffer), fp);
        fclose(fp);
    }
    else printf("No permission \n");
}
```

**用户程序分析:**

**1。**上面给出的程序是一个根用户拥有的程序，它是一个 Set-UID 程序，也就是一个特权程序。

**2。**程序的功能是将用户输入的字符串附加到我们创建的文件 */tmp/XYZ* 的末尾。

**3。**给定的代码以根权限运行，因此它的有效用户标识( *euid* )等于 0。它对应于一个根，因此可以覆盖任何文件。

**4。**使用*访问()*系统调用，程序防止自己意外覆盖别人的文件。它首先使用 access()调用检查真实用户 ID [uid]是否具有文件/tmp/XYZ 的适当访问权限。

**5。**如果检查结果为真，并且真实用户标识确实具有权限，则程序会打开文件并将用户输入附加到文件中。

**6。**在 *fopen()* 的系统调用中有一个额外的检查，但它只检查 *euid(有效用户 ID)* 而不是 *uid(真实用户 ID)* ，作为一个特权程序，它总是被满足的，因为该程序作为一个 Set-UID 程序(特权程序)运行，其 *euid* 为 0(根用户)。

**7。**现在，可能发生的实际错误点可能是由于要写入的文件的检查“ *access()* 和使用“ *fopen()* ”之间的时间窗口。 *access()* 系统调用使用的文件很可能与 *fopen()* 系统调用使用的文件不同。

**8。**只有当恶意攻击者能够以某种方式使 */tmp/XYZ* 成为一个“**符号链接**”来指向一个受保护的文件时，这才是可能的，否则该文件就像 */etc/shadow* (它包含我们的密码)一样无法在使用时间窗口(TOCTOU 窗口)的检查时间内访问。

```
unlink("/tmp/XYZ");
symlink("/etc/passwd","/tmp/XYZ");
```

**9。**如果成功，攻击者可以将用户输入附加到 */etc/shadow* 的末尾，而不是*符号链接的原始目标，*就像创建一个拥有所有权限的新根用户一样，只需将一条语句附加到 *shadow* 文件。

**10。**因此，该窗口会导致竞争条件漏洞。

因此，有可能在两个系统调用(即 access()和 open()之间进行上下文切换，也有可能存在竞争条件漏洞。

**攻击程序代码:**

```
#include<unistd.h>
int main(){
    while(1){
        unlink("/tmp/XYZ");
        symlink("/home/seed/myfile", "/tmp/XYZ");
        usleep(10000);

        unlink("/tmp/XYZ");
        symlink("/etc/passwd", "/tmp/XYZ");
        usleep(10000);
        }
    return 0;
}
```

该程序旨在通过使用 *usleep(10000)* 展示钢筋混凝土，因此有意创建一个 TOCTOU 窗口。

*   这里我们正在创建一个*符号链接*到一个我们普通用户拥有的文件(my file)，所以要通过*访问()*检查。
*   然后生成一个窗口，让我们休眠 10000 微秒，让我们易受攻击的进程运行。
*   然后*取消*与*符号链接*的链接，并创建一个*符号链接*到 */etc/passwd。*

**应对措施:**

**1。应用最小特权原则:**
根据该原则，我们尝试对 Set-UID 程序的所有部分降低文件的特权。特别是不需要提升特权的。为此，我们使用 *geteuid* 和 *seteuid* 系统调用来降级，然后在易受攻击程序的适当位置重新升级权限。

**2。Ubuntu 内置保护方法:**

```
$ sudo sysctl -w kernel.yama.protected_sticky_symlinks=1
```

**3。系统调用的重复检查:**
竞争条件更多的是概率性的，而不是确定性的(我们无法确定何时能够访问文件，它可能发生在 TOCTOU 检查窗口内的任何实例中)。使用对 *access()* 和 *open()* 系统调用的重复检查，我们可以匹配文件的 *inode* 值。虽然这个值在每次检查中是相同的，但是我们可以说文件是打开的，如果它不同，这意味着文件被更改了，我们不会打开它。

**4。原子操作:**

```
f = open(file, O_CREAT | O_EXCL)
```

如果文件已经存在，那么上面提到的这两个说明符将不会打开指定的文件。因此实现了检查的原子性和文件的使用。

参考文献和源代码:锡拉丘兹大学种子实验室。