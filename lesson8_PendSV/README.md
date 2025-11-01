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

Systick will preempt ISR only if its priority is higher than ISR.Here we assumed it to be higher.  
<img width="1122" height="648" alt="image" src="https://github.com/user-attachments/assets/8d35a42c-f314-4223-9717-8c052a1fead1" />  

---

## Use cases
1)Offloading interrupt processing.  
2)If high priority handler is doing time consuming work then other lower priority interrupts will suffer and systems responsiveness may reduce.This can be solved by 
using combination of ISR and PendSV.  

---

## Offloading interrupt processing 
1)First half is time critical needs to be executed as part of ISR.  
2)second half is bottom half basically delayed execution where rest of time consuming work will be done.  
3)The ISR (first half) performs time-critical actions and then sets the PendSV pending bit to schedule the bottom half. The PendSV handler (second half) executes the deferred processing at the lowest priority, ensuring minimal ISR latency.  

<img width="1014" height="544" alt="image" src="https://github.com/user-attachments/assets/2533b4fb-18d1-4cd7-93a2-057eadaafce0" />



