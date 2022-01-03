# 8086 程序反转一串

> 原文:[https://www . geesforgeks . org/8086-程序转反串/](https://www.geeksforgeeks.org/8086-program-to-reverse-a-string/)

**问题:**给定一个字符串，我们必须反转该字符串并打印反转后的字符串。
**例:**

```
Input: String : "This is a sample string"
Output: gnirts elpmas a si sihT

Input: String : "Geeks for Geeks"
Output: skeeG rof skeeG 
```

**说明:**

1.  创建字符串
2.  穿过绳子
3.  推入堆栈中的字符
4.  计算字符数
5.  加载字符串的起始地址
6.  弹出堆栈的顶部字符，直到计数不等于零
7.  输入字符，减少计数，增加地址
8.  继续，直到计数大于零
9.  使用 LEA 命令在 dx 中加载字符串的有效地址
10.  通过在 AH 中用 9H 调用中断来打印刺痛
11.  该字符串必须以“{content}”结尾。符号

**节目:**

## 卡片打印处理机（Card Print Processor 的缩写）

```
.MODEL SMALL
.STACK 100H
.DATA

; The string to be printed
STRING DB 'This is a sample string', '{content}apos;

.CODE
MAIN PROC FAR
MOV AX,@DATA
MOV DS,AX

; call reverse function
CALL REVERSE

; load address of the string
LEA DX,STRING

; output the string
; loaded in dx
MOV AH, 09H
INT 21H

; interrupt to exit
MOV AH, 4CH
INT 21H

MAIN ENDP
REVERSE PROC
    ; load the offset of
    ; the string
    MOV SI, OFFSET STRING

    ; count of characters of the;
    ;string
    MOV CX, 0H

    LOOP1:
    ; compare if this is;
    ;the last character
    MOV AX, [SI]
    CMP AL, '{content}apos;
    JE LABEL1

    ; else push it in the;
    ;stack
    PUSH [SI]

    ; increment the pointer;
    ;and count
    INC SI
    INC CX

    JMP LOOP1

    LABEL1:
    ; again load the starting;
    ;address of the string
    MOV SI, OFFSET STRING

        LOOP2:
        ;if count not equal to zero
        CMP CX,0
        JE EXIT

        ; pop the top of stack
        POP DX

        ; make dh, 0
        XOR DH, DH

        ; put the character of the;
        ;reversed string
        MOV [SI], DX

        ; increment si and;
        ;decrement count
        INC SI
        DEC CX

        JMP LOOP2

    EXIT:
    ; add $ to the end of string
    MOV [SI],'$ '
    RET

REVERSE ENDP
END MAIN
```

**输出:**

```
gnirts elpmas a si sihT
```

**注意:**
该程序无法在在线编辑器上运行，请使用 MASM 运行该程序，使用 dos box 运行 MASM，您可以使用任何 8086 仿真器运行该程序。