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
