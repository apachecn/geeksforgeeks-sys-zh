# 从子程序返回和从中断返回

> 原文:[https://www . geesforgeks . org/子程序返回和中断返回/](https://www.geeksforgeeks.org/return-from-subroutine-and-return-from-interrupt/)

在本文中，我们将讨论从子程序返回和从中断返回，并详细解释，最后以子程序返回和从中断返回的区别结束。我们一个一个来讨论。

**从子程序返回:**

*   Returning from the subroutine is to return the execution of the code to the state before calling the subroutine.
*   Usually, the subroutine is called by the **[call** instruction. At each CALL instruction, the IP and CS of the next instruction are pushed onto the stack, and then control is transferred to the procedure. At the end of the program, the **' ret'** instruction must be executed.
*   RET is used to return from the subroutine previously CALLed by call. When it is executed, the previously stored contents such as IP and CS are retrieved from the stack into **CS and IP** registers, and the execution of the main program continues further.
*   Therefore, it is assumed that calling the subroutine will push the current address PC+2 onto the stack. Returning from the subroutine will return the address calculated by the top two bytes of the stack.
*   First, the most significant byte is popped from the stack, then the least significant byte. The address of RET is loaded from the stack. After RET is executed, the stack and its pointer will be modified accordingly.

**从中断返回:**

*   Returning from the interrupt is to return the code execution to the state before the interrupt, and at the same time, to save the flag in the flag register.
*   Usually, when an interrupt occurs, it is handled by calling its own service routine. When the interrupt service routine is to be called, before transferring control to it, IP, CS and flags are stored on the stack together to indicate the position where the interrupt service routine ( **ISR** ) continues to be executed after execution. Therefore, at the end of ISR, execute **' iret** ', retrieve the values of IP, CS and flag from the stack, and continue the execution of the main program.
*   IRET or **reti** is used to return from ISR. It first loads the flag from the stack and restores its previous value, that is, it enables flag interrupt. After loading the flag from the stack, it will load the CS and IP values from the stack into the register, and the execution of the main program will continue. Use **[Pushf]** and **[POPF]** instructions to push and eject the flag from the stack respectively. Load the IRET address from the stack and enable the global interrupt flag. After IRET is executed, the stack and its pointer are modified accordingly.

**从子程序返回和从中断返回的区别:**

1.  The IRET instruction is used to exit the interrupt program, while RET is used to return from the subroutine.
2.  IRET is similar to RET, except that RET will only pop two bytes to the PC, while IRET will reset the interrupt enable ( **ien** ) trigger and pop two bytes from the stack.
3.  To tell the processor that the interrupt processing is over, the flag can be reset, and the IRET instruction is used instead of just RET.
4.  If executed outside ISR, IRET has the same function as RET.