# Scheduler
1)Scheduler using round robin carry out context switch operation.  
2)Round robin scheduling method is like time slice are assigned to each task in equal portions and in circular order.  
3)First we will use systick handler to do context switch and then will use PendSV handler.

---

## What is Task
1)Task is nothing but piece of code or our C function doing specific job.  
2)Task has its own stack to create its local variables when run on CPU.When scheduler decides to remove task from CPU,scheduler first saves context of tasks private task.  
3)Task never loses its state until it is deleted permanantly.

---

## Stack Assessment 
1)In memory map of processor SRAM starts at 0x20000000 and its size is 128KB.  
2)Stack in assembly is Full Descending(FD) in nature.That means stack would start from top of SRAM that is SRAM_END.  
3)Scheduling is an algorithm which takes decision of pre-empting a running task from CPU and takes decision about which task should run on CPU next.  
4)State of task consist of general purpose registers,some special and status registers because this are the one who stores data before pre-empting from one task.

---

## Systick Reload value register
1)Systick is a down counter.The reload value register specifies start value to load into SYST_CVR register.  
2)Reload value stores the count value and the moment we enable timer the value gets copied to CVR register.  
3)When this register content reach 0 again new value get reloaded in it.  
4)Exception doesn't happen at 0 it happen when CVR reloaded with new value.So for Nth cycle excpetion we should store N-1 count value.  
5)If systick exception required for every 100th pulses reload to 99.

---

## Systick control and status register


