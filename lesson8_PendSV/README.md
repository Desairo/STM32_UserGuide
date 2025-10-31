# PendSV Exception
1)It is an exception type 14.It has programmable priority level.  
2)Exception is triggered by setting its pending status by writing to the Interrupt Control and State Register.  
3)Triggering pendSV system exception is a way of invoking the premptive kernel to carry out context switch in OS.  
4)In OS,pendSV handler is set to the lowest priority level and the pendSV handler carries out context switch operation.

---

## Important pendSV Information
1)This exception is triggered in high priority exception handler and it gets executed when higher priority handler finishes.  
2)With this schedule pendSV to be executed after all interrupt done.  
3)PendSV useful in interrupt noisy environment and we need to delay context switching until all IRQ executed.  
4)Context switch refers to storing context of current task.
