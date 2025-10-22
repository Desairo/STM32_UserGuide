## Reset sequence of cortex processor 
1)Then processor first reads value at location 0x0000_0000 in to MSP(Main Stack Pointer).This is intialisation of stack pointer.  
2)After that processor reads value at location 0x0000_0004 in to PC.This value is address of reset handler.  
3)PC jumps to reset handler which is function that carry out any initialisation required and then call main function.

---

## Access level of teh processor 
1)It's restricted to go from an unprivileged access mode to privileged or handler mode.This is because security risks 
are produced here by this task.Also unprivileged codes are usually application code that shouldn't have ability to control 
system level operations.  
2)To make thread mode unprivileged,modify control register nPRIV to 1.  
3)User task should not modify some of the system level processor or not trigger any interrupt.If unprivileged mode wants 
any services from privileged mode it can trigger a system call which will be serviced by kernel code.  
4)Once interrupt is triggered it change itself to handler mode which is in privileged mode then it will exit to thread mode.

---

## Importance of T bit 
1)Arm uses 32-bit wide instructions providing high performance and efficient execution.THUMB instruction set uses 16-bit wide 
instructions.This smaller instruction size leads to more compact code beneficial for reducing memory usage.  
2)T bit is 0 represent ARM instruction whereas 1 represent THUMB instruction.Usually cortex processors works on THUMB instruction.  
3)Whenever we load value or address into PC bit 0 of value is loaded into T bit.Thus any address loaded in PC must have oth bit 
1.So,address should be odd.  
3)Hard fault is detected when it finds oth bit is 0.Compiler automatically convert 0 to 1.
