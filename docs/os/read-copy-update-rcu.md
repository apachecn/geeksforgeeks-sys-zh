# 读拷贝更新(RCU)

> 原文:[https://www.geeksforgeeks.org/read-copy-update-rcu/](https://www.geeksforgeeks.org/read-copy-update-rcu/)

Linux 内核中广泛使用的一种**锁原语**是读拷贝更新(RCU)锁。这是一种同步机制，于 2002 年 10 月添加到 Linux 内核中。它通过使读取与更新同时发生而实现了改进。它支持多个读取器和单个更新器之间的并发。RCU 的读取端原语没有开销。它是最安全的数据结构之一，旨在同时访问期间安全运行，因为它有效地使用了缓存线和内存。

**读拷贝更新(CPU)** 锁有一个无锁读临界区。RCU 锁适用于编写器与无锁读取器兼容的工作负载。在读取临界区不允许抢占。

考虑以下代码:

```
struct Node
{

  int key, val;       

  /* pointer to the "next" and "prev"(previous) node */         
  struct Node *next, *prev;    

}

/* Searches for a given key node in a list li and, 
 returns the value corresponding to that key*/
int search(struct Node *li, int key)  
{
    int ret= -1;
    preempt_disable(); 

    /* Disabling the preempt */ 
    while(li!=NULL)
    {

      /* The required key is found */
      if(li->key == key)   
      {

        /* Assigning "ret" the value of that particular key */
        ret = li->val;     
        break;

      }

     /* moving on to the next list value */
     li=li->next;       

     }

    /* Enabling the interrupt which was disabled earlier */
    preempt_enable();  

    /* Return the value of the key that is found */
    return ret;       

}

/* Deletes a given node */
void delete (struct Node *node)     
{

  /* Take a spin lock on the given node */ 
  spin_lock(&lock);              
  node->next->prev = node->prev;   
  node->prev->next = node->next;

  /* Unlock the lock on the node, 
   because the deletion has been done */
  spin_unlock(&lock);            
  free(node); 

}
```

在上面的代码中，next(即 node->prev->next = node->next)的删除更新是原子的，因为存储操作是原子的。如果同时执行删除，搜索例程将根据下一步是否更新，看到新列表或旧列表。此外，删除操作可以与搜索操作同时执行，因为与搜索相关的更新是链表节点的下一个字段的更新。

在读复制更新方案中，自由操作被延迟，直到更新者 100 %确定其他线程没有对将要被删除的对象的引用。由于在读关键部分不允许抢占，调用 RCU 调度表明特定核心没有执行读关键部分。

在 RCU 方案中，一个作者称 **rcu_free** 而不是 **free** 。rcu_free 确保在调用 rcu_free 后，所有读取器都至少从其关键部分退出一次。该检查确保其他线程没有对将要删除的对象的活动引用。

当 **rcu_free** 调用 **wait_for_rcu** 时，这就完成了，wait_for_rcu 调度所有内核上的当前线程，为挂起的空闲强制一个安全点。

**优点和缺点:**
RCU 锁不能用于像 Tree 这样的数据结构，因为 Tree 搜索可能依赖于不能自动完成的多次更新。

读拷贝更新锁的一个缺点是它需要禁止抢占，因此它们不能在**用户模式**中使用。