# Scheduler
1)Scheduler using round robin carry out context switch operation.  
2)Round robin scheduling method is like time slice are assigned to each task in equal portions and in circular order.  
3)First we will use systick handler to do context switch and then will use PendSV handler.

---

## What is Task
1)Task is nothing but piece of code or our C function doing specific job.  
2)Task has its own stack to create its local variables when run on CPU.When scheduler decides to remove task from CPU,scheduler first saves context of tasks private task.  
3)Task never loses its state until it is deleted permanantly.
