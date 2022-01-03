# 8086 程序打印字符串

> 原文:[https://www . geesforgeks . org/8086-程序转打印字符串/](https://www.geeksforgeeks.org/8086-program-to-print-a-string/)

**问题:**编写汇编级程序打印给定字符串。

**示例:**

```
Input String: "This is a sample string" 
Output: This is a sample string

Input String: "Geeks for Geeks" 
Output: Geeks for Geeks 
```

**说明:**

1.  创建字符串
2.  使用 LEA 命令在 dx 中加载字符串的有效地址
3.  通过在 AH 中用 9H 调用中断来打印字符串
4.  该字符串必须以“{content}”结尾。符号

**程序**

```
.MODEL SMALL 
.STACK 100H 
.DATA 

;The string to be printed 
STRING DB 'This is a sample string', '{content}apos;

.CODE 
MAIN PROC FAR 
 MOV AX,@DATA 
 MOV DS,AX 

 ; load address of the string 
 LEA DX,STRING 

 ;output the string
 ;loaded in dx 
 MOV AH,09H
 INT 21H 

 ;interrupt to exit
 MOV AH,4CH
 INT 21H 

MAIN ENDP 
END MAIN 
```

**输出:**

```
This is a sample string 
```

**注意:**
该程序无法在在线编辑器上运行，请使用 MASM 运行该程序，使用 dos box 运行 MASM，您可以使用任何 8086 仿真器运行该程序。