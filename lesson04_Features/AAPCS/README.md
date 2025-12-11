# AAPCS(Arm Architecture Procedure Call Standard)
AAPCS describes procedure call standard used by application binary interface(ABI) for ARM architecture.AAPCS defines how subroutines 
can be seperately written,compiled and assembled to work.It describes contract between calling routine and called routine.

1)Obligations on caller to create program state in which called routine may start to execute.  
2)Obligations on called routine to preserve the program state of the caller across the call.  
3)The rights of called routine to alter the program state of its caller.  
4)When C compiler compiles code it should follow AAPCS.According to this standard C function can modify registers.  
5)Its responsibility of function caller to save this register on stack before calling function if those values still be needed 
further in function call and retrive back once called function returns.  
6)R4-R11 called callee registers.Function being called needs to make sure that content of this registers will be unaltered before 
exiting function.  
7)Caller use R0,R1,R2 and R3 to send input to callee.Callee uses R0 and R1 to send result back to caller.  
8)If arguments to be passed are more than the above 4 then rest will be passed through stack.

---

## Stack activities during interrupt
1)To work in case of exception handler,there is need to save all registers and restore them at exception exit under control of processor hardware.  
2)When returned to interrupted program all registers would have same value as when interrupt sequence started.  
3)There is no any caller for interrupt.It is called by hardware.So no any AAPCS rules need to be followed and whenever exception comes stacking happens.
