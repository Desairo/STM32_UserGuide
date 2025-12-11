# 🧵 Scheduler

1) A scheduler using **Round Robin** performs task switching through context switching.  
2) In Round Robin scheduling, **equal time slices** are assigned to each task in circular order.  
3) First, we use the **SysTick handler** to perform context switching, and later switch to the **PendSV handler**.

---

## 🧠 What is a Task?

1) A **task** is simply a piece of code or a C function that performs a specific job.  
2) Every task has its **own stack**, used to store local variables during execution.  
   When the scheduler pre-empts a task, it first **saves the task’s context** on its private stack.  
3) A task **never loses its state** unless it is deleted permanently.

---

## 🗂️ Stack Assessment

1) In the processor memory map, **SRAM starts at `0x20000000`**, with a size of **128 KB**.  
2) The stack in ARM Cortex-M follows a **Full Descending (FD)** model, meaning it grows downward starting from **SRAM_END**.  
3) Scheduling is the algorithm that decides **when to pre-empt a running task** and **which task should execute next**.  
4) A task’s state consists of **general-purpose registers, special registers, and status registers**, as these store important data before a context switch.

---

## ⏱️ SysTick Reload Value Register

1) SysTick is a **down counter**. The reload value register specifies the initial value loaded into the **SYST_CVR** register.  
2) When SysTick is enabled, the reload value is copied into **CVR**.  
3) Once CVR reaches zero, it is automatically **reloaded** with the value from the reload register.  
4) The exception does **not** occur at zero — it occurs **when CVR reloads**.  
   Hence, for an exception every *N* cycles, store **N − 1**.  
5) Example: For a SysTick exception every **100 pulses**, load **99**.

---

## ⚙️ SysTick Control and Status Register

1) **Bit 0** enables the counter.  
2) **Bit 1** enables the SysTick exception request.  
3) **Bit 2** selects the clock source.
