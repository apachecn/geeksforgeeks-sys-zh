# 8086 程序查找两个数字的 GCD 并打印 GCD

> 原文:[https://www . geeksforgeeks . org/8086-两个数字的程序查找和打印 gcd/](https://www.geeksforgeeks.org/8086-program-to-find-gcd-of-two-numbers-and-print-the-gcd/)

**问题:**给我们两个十进制数，我们要找到两个数的 GCD，并以十进制格式打印 GCD。
参考[找到两个数字的 GCD](https://www.geeksforgeeks.org/c-program-find-gcd-hcf-two-numbers/)。

**示例:**

```
Input: d1 = 16, d2 = 24
Output: GCD = 8

Input: d1 = 12, d2 = 18
Output: GCD = 6 
```

**说明:**

1.  ax 中的负载值 d1 和 bx 中的负载值 d2
2.  调用 gcd 函数
3.  如果 bx 中的值为零
4.  然后将 gcd ( CX)的值设置为 ax
5.  否则，将 ax 的值设置为 bx，将 bx 的值设置为 ax % bx
6.  递归调用 gcd 函数
7.  将 cx 的值载入 ax
8.  调用打印功能打印两个数字的 gcd

**程序:**

```
.MODEL SMALL
    .STACK 100H
    .DATA
        d1 dw 16 d2 dw 24
    .CODE
        MAIN PROC FAR
            MOV AX,
    @DATA
        MOV DS,
    AX

;initialize ax and bx
    mov bx,
    d2
        mov ax,
    d1

;find gcd of two numbers
    call gcd

;load the gcd in ax
    mov ax,
    cx

;print the value
    CALL PRINT

;interrupt to exit
    MOV AH,
    4CH INT 21H

    MAIN ENDP
        GCD PROC

;if
    bx is 0 cmp bx, 0 jne continue

;then gcd is ax
    mov cx,
    ax
        ret

    continue:

;else gcd(b, a % b)
    xor dx,
    dx

;divide ax by bx
    div bx

;initialize ax as bx
    mov ax,
    bx

;and 
bx as ax % bx
    mov bx,
    dx

;recursively call gcd
    call GCD
        ret
            GCD ENDP
                PRINT PROC

;initialize count
    mov cx,
    0 mov dx, 0 label1:

;if
    ax is zero
        cmp ax,
        0 je print1

;initialize bx to 10 mov bx, 10

;extract the last digit
    div bx

;push it in the stack
    push dx

;increment the count
    inc cx

;set dx to 0
    xor dx,
    dx
        jmp label1
            print1:

;check if count
;is greater than zero
    cmp cx,
    0 je exit

;pop the top of stack
    pop dx

;add 48 so that it
;represents the ASCII
;value of digits
    add dx,
    48

;interrupt to print a
;character
    mov ah,
    02h int 21h

;decrease the count
    dec cx
        jmp print1
            exit : ret
                       PRINT ENDP
                           END MAIN
```

**输出:**

```
8
```

**注意:**该程序不能在在线编辑器上运行，请使用 MASM 运行该程序，使用 dos 框运行 MASM，您可以使用任何 8086 仿真器运行该程序