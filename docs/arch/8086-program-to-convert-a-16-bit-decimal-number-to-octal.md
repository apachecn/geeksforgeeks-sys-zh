# 8086 将 16 位十进制数转换为八进制数的程序

> 原文:[https://www . geesforgeks . org/8086-程序转转换-16 位十进制数转八进制/](https://www.geeksforgeeks.org/8086-program-to-convert-a-16-bit-decimal-number-to-octal/)

**问题:**给我们一个 16 位的十进制数，我们必须以八进制格式打印这个数。

**例:**

```
Input: d1 = 16
Output:20

Input: d1 = 123
Output: 173 
```

**说明:**

1.  Load the stored value into the register.
2.  Divide the value by 8 to octal.
3.  Pushing remainder onto stack
4.  Increase the count
5.  Repeat the above steps until the register value is greater than 0.
6.  Until the count is greater than zero.
7.  Eject stack
8.  Add 48 to the top element and convert it to ASCII.

**程序:**

```
;8086 program to convert a 16 bit decimal number to octal
    .MODEL SMALL
    .STACK 100H
    .DATA
        d1 dw 16
    .CODE
        MAIN PROC FAR
            MOV AX,
    @DATA
        MOV DS,
    AX

;load the value stored;
in variable d1
    mov ax,
    d1

;convert the value to octal;
print the value
    CALL PRINT

;interrupt to exit
    MOV AH,
    4CH INT 21H

    MAIN ENDP
        PRINT PROC

;initialize count
    mov cx,
    0 mov dx, 0 label1:;
if
    ax is zero
        cmp ax,
        0 je print1

;initialize bx to 8 mov bx, 8

;divide it by 8;
to convert it to octal
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
20
```

**注意:**该程序无法在在线编辑器上运行，请使用 MASM 运行该程序，使用 dos box 运行 MASM，您可以使用任何 8086 仿真器运行该程序。