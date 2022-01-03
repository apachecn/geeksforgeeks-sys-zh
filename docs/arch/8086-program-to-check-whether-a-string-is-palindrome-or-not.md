# 8086 检查字符串是否回文的程序

> 原文:[https://www . geesforgeks . org/8086-程序检查字符串是否是回文/](https://www.geeksforgeeks.org/8086-program-to-check-whether-a-string-is-palindrome-or-not/)

**问题:**写一个 8086 程序，检查给定的字符串是否回文。
**例:**

```
Input String: "abba"
Output: String is palindrome

Input String: "abbca"
Output: String is not palindrome 
```

**说明:**

1.  创建字符串
2.  遍历到字符串的末尾
3.  获取字符串末尾的地址
4.  加载字符串的起始地址
5.  比较存储在地址中的值
6.  增加指针
7.  递减指针
8.  再次比较存储在 si 和 di 中的值
9.  重复上述步骤，直到 SI<=DI
10.  如果所有字符匹配，打印字符串是回文，否则打印不是回文

**节目:**

## 卡片打印处理机（Card Print Processor 的缩写）

```
.MODEL SMALL
.STACK 100H
.DATA

; The string to be printed
STRING DB 'abba', '{content}apos;
STRING1 DB 'String is palindrome', '{content}apos;
STRING2 DB 'String is not palindrome', '{content}apos;

.CODE
MAIN PROC FAR
 MOV AX, @DATA
 MOV DS, AX

 ; check if the string is;
 ;palindrome or not
 CALL Palindrome

 ;interrupt to exit
 MOV AH, 4CH
 INT 21H
 MAIN ENDP
 Palindrome PROC

 ; load the starting address
 ; of the string
 MOV SI,OFFSET STRING

 ; traverse to the end of;
 ;the string
 LOOP1 :
    MOV AX, [SI]
    CMP AL, '{content}apos;
    JE LABEL1
    INC SI
    JMP LOOP1

 ;load the starting address;
 ;of the string
 LABEL1 :
    MOV DI,OFFSET STRING
    DEC SI

    ; check if the string is palindrome;
    ;or not
    LOOP2 :
     CMP SI, DI
     JL OUTPUT1
     MOV AX,[SI]
     MOV BX, [DI]
     CMP AL, BL
     JNE OUTPUT2

    DEC SI
    INC DI
    JMP LOOP2

 OUTPUT1:
    ;load address of the string
    LEA DX,STRING1

    ; output the string;
    ;loaded in dx
    MOV AH, 09H
    INT 21H
    RET

 OUTPUT2:
    ;load address of the string
    LEA DX,STRING2

    ; output the string
    ; loaded in dx
    MOV AH,09H
    INT 21H
    RET

Palindrome ENDP
END MAIN
```

**输出:**

```
String is palindrome
```

**注意:**
该程序无法在在线编辑器上运行，请使用 MASM 运行该程序，使用 dos box 运行 MASM，您可以使用任何 8086 仿真器运行该程序。