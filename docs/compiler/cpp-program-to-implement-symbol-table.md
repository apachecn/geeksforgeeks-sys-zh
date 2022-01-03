# 实现符号表的 C++程序

> 原文:[https://www . geesforgeks . org/CPP-程序到实现-符号-表/](https://www.geeksforgeeks.org/cpp-program-to-implement-symbol-table/)

**先决条件:** [符号表](https://www.geeksforgeeks.org/symbol-table-compiler/)

一个*符号表*是一个由编译器使用的数据结构，其中程序源代码中的每个标识符连同与其相关联的与其声明相关的信息一起被存储。它存储标识符及其相关属性，如范围、类型、出现行数等。

符号表可以使用各种数据结构来实现，例如:

*   链接列表
*   散列表
*   树

用于实现符号表的常见数据结构是哈希表。

**符号表**的操作–符号表中定义的基本操作包括:
![](img/e0b66a00df56e4f332b469fc5e3f61e8.png)

考虑以下 C++函数:

> //定义一个全局函数
> int add(int a，int b)
> {
> int sum = 0；
> 总和= a+b；
> 归还款子；
> }

**上述代码符号表:**

| 名字 | 类型 | 范围 |
| 增加 | 功能 | 全球的 |
| a | （同 Internationalorganizations）国际组织 | 功能参数 | b | （同 Internationalorganizations）国际组织 | 功能参数 | 总和 | （同 Internationalorganizations）国际组织 | 当地的 |

下面是符号表的 C++实现，使用了[散列和单独链接](https://www.geeksforgeeks.org/hashing-set-2-separate-chaining/)的概念:

```
// C++ program to implement Symbol Table
#include <iostream>
using namespace std;

const int MAX = 100;

class Node {

    string identifier, scope, type;
    int lineNo;
    Node* next;

public:
    Node()
    {
        next = NULL;
    }

    Node(string key, string value, string type, int lineNo)
    {
        this->identifier = key;
        this->scope = value;
        this->type = type;
        this->lineNo = lineNo;
        next = NULL;
    }

    void print()
    {
        cout << "Identifier's Name:" << identifier
             << "\nType:" << type
             << "\nScope: " << scope
             << "\nLine Number: " << lineNo << endl;
    }
    friend class SymbolTable;
};

class SymbolTable {
    Node* head[MAX];

public:
    SymbolTable()
    {
        for (int i = 0; i < MAX; i++)
            head[i] = NULL;
    }

    int hashf(string id); // hash function
    bool insert(string id, string scope,
                string Type, int lineno);

    string find(string id);

    bool deleteRecord(string id);

    bool modify(string id, string scope,
                string Type, int lineno);
};

// Function to modify an identifier
bool SymbolTable::modify(string id, string s,
                         string t, int l)
{
    int index = hashf(id);
    Node* start = head[index];

    if (start == NULL)
        return "-1";

    while (start != NULL) {
        if (start->identifier == id) {
            start->scope = s;
            start->type = t;
            start->lineNo = l;
            return true;
        }
        start = start->next;
    }

    return false; // id not found
}

// Function to delete an identifier
bool SymbolTable::deleteRecord(string id)
{
    int index = hashf(id);
    Node* tmp = head[index];
    Node* par = head[index];

    // no identifier is present at that index
    if (tmp == NULL) {
        return false;
    }
    // only one identifier is present
    if (tmp->identifier == id && tmp->next == NULL) {
        tmp->next = NULL;
        delete tmp;
        return true;
    }

    while (tmp->identifier != id && tmp->next != NULL) {
        par = tmp;
        tmp = tmp->next;
    }
    if (tmp->identifier == id && tmp->next != NULL) {
        par->next = tmp->next;
        tmp->next = NULL;
        delete tmp;
        return true;
    }

    // delete at the end
    else {
        par->next = NULL;
        tmp->next = NULL;
        delete tmp;
        return true;
    }
    return false;
}

// Function to find an identifier
string SymbolTable::find(string id)
{
    int index = hashf(id);
    Node* start = head[index];

    if (start == NULL)
        return "-1";

    while (start != NULL) {

        if (start->identifier == id) {
            start->print();
            return start->scope;
        }

        start = start->next;
    }

    return "-1"; // not found
}

// Function to insert an identifier
bool SymbolTable::insert(string id, string scope,
                         string Type, int lineno)
{
    int index = hashf(id);
    Node* p = new Node(id, scope, Type, lineno);

    if (head[index] == NULL) {
        head[index] = p;
        cout << "\n"
             << id << " inserted";

        return true;
    }

    else {
        Node* start = head[index];
        while (start->next != NULL)
            start = start->next;

        start->next = p;
        cout << "\n"
             << id << " inserted";

        return true;
    }

    return false;
}

int SymbolTable::hashf(string id)
{
    int asciiSum = 0;

    for (int i = 0; i < id.length(); i++) {
        asciiSum = asciiSum + id[i];
    }

    return (asciiSum % 100);
}

// Driver code
int main()
{
    SymbolTable st;
    string check;
    cout << "**** SYMBOL_TABLE ****\n";

    // insert 'if'
    if (st.insert("if", "local", "keyword", 4))
        cout << " -successfully";
    else
        cout << "\nFailed to insert.\n";

    // insert 'number'
    if (st.insert("number", "global", "variable", 2))
        cout << " -successfully\n\n";
    else
        cout << "\nFailed to insert\n";

    // find 'if'
    check = st.find("if");
    if (check != "-1")
        cout << "Identifier Is present\n";
    else
        cout << "\nIdentifier Not Present\n";

    // delete 'if'
    if (st.deleteRecord("if"))
        cout << "if Identifier is deleted\n";
    else
        cout << "\nFailed to delete\n";

    // modify 'number'
    if (st.modify("number", "global", "variable", 3))
        cout << "\nNumber Identifier updated\n";

    // find and print 'number'
    check = st.find("number");
    if (check != "-1")
        cout << "Identifier Is present\n";
    else
        cout << "\nIdentifier Not Present";

    return 0;
}
```

**Output:**

```
**** SYMBOL_TABLE ****

if inserted -successfully
number inserted -successfully

Identifier's Name:if
Type:keyword
Scope: local
Line Number: 4
Identifier Is present

if Identifier is deleted

number Identifier updated

Identifier's Name:number
Type:variable
Scope: global
Line Number: 3
Identifier Is present

```