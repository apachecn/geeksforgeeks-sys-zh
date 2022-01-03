# 8086 程序打印 16 位十进制数

> 原文:[https://www . geesforgeks . org/8086-程序打印一个 16 位十进制数/](https://www.geeksforgeeks.org/8086-program-to-print-a-16-bit-decimal-number/)

**问题:**编写 8086 程序打印 16 位十进制数。

**示例:**

```
Input: d1 = 655
Output: 655

Input: d1 = 234
Output:234 
```

**说明:**

1.  将存储的值载入寄存器
2.  将该值除以 10
3.  将剩余部分推入堆栈
4.  增加计数
5.  重复这些步骤，直到寄存器的值大于 0
6.  直到计数大于零
7.  打开堆栈
8.  在顶部元素中添加 48，将其转换为 ASCII
9.  使用中断打印字符
10.  递减计数

**程序:**

## 澳大利亚工党

```
;8086 program to print a 16 bit decimal number
.MODEL SMALL
.STACK 100H
.DATA
d1 dw 655
.CODE
MAIN PROC FAR
    MOV AX,@DATA
    MOV DS,AX   

    ;load the value stored
    ; in variable d1
    mov ax,d1      

    ;print the value
    CALL PRINT     

    ;interrupt to exit              
    MOV AH,4CH
    INT 21H

MAIN ENDP
PRINT PROC          

    ;initialize count
    mov cx,0
    mov dx,0
    label1:
        ; if ax is zero
        cmp ax,0
        je print1     

        ;initialize bx to 10
        mov bx,10       

        ; extract the last digit
        div bx                 

        ;push it in the stack
        push dx             

        ;increment the count
        inc cx             

        ;set dx to 0
        xor dx,dx
        jmp label1
    print1:
        ;check if count
        ;is greater than zero
        cmp cx,0
        je exit

        ;pop the top of stack
        pop dx

        ;add 48 so that it
        ;represents the ASCII
        ;value of digits
        add dx,48

        ;interrupt to print a
        ;character
        mov ah,02h
        int 21h

        ;decrease the count
        dec cx
        jmp print1
exit:
ret
PRINT ENDP
END MAIN
```

**输出:**

```
655
```

**注意:**该程序不能在在线编辑器上运行，请使用 MASM 运行该程序，使用 dos 框运行 MASM，您可以使用任何 8086 仿真器运行该程序