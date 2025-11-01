# PendSV Exception
1)It is an exception type 14.It has programmable priority level.  
2)Exception is triggered by setting its pending status by writing to the Interrupt Control and State Register.  
3)Triggering pendSV system exception is a way of invoking the premptive kernel to carry out context switch in OS.  
4)In OS,pendSV handler is set to the lowest priority level and the pendSV handler carries out context switch operation.

---

## Important pendSV Information
1)This exception is triggered in high priority exception handler and it gets executed when higher priority handler finishes.  
2)PendSV is executed after all interrupt done.  
3)PendSV useful in interrupt noisy environment and we need to delay context switching until all IRQ executed.  
4)Context switch refers to storing context of current task and retriving context of new task.  
5)More precisely in reality data is not saved or context is not switched in systick timer/scheduler rather it is done in PendSV handler. 
6)Systick will only preempt ISR only if its priority is higher than ISR.

---

Shift from task A context go to scheduler spend some time to save data and then retrive data from task B.  
<img width="869" height="399" alt="image" src="https://github.com/user-attachments/assets/eb0f5579-7b3a-4ecf-bea6-b6fe9d7e24c5" />  


