# 🧭 Operation Modes of the ARM Cortex Processor

The ARM Cortex processor operates in different **modes** to handle application execution, privileged operations, and interrupt processing.  
These modes determine **access level**, **security**, and **execution behavior**.

There are two primary modes:

1. **Thread Mode**  
2. **Handler Mode**

---

## 🧵 Thread Mode

- Used for **normal application code execution**.  
- The processor **starts in Thread Mode** after reset.  
- Execution here can be:
  - **Privileged** → full access to memory, registers, and system resources.  
  - **Unprivileged** → restricted access, used for application/user-level tasks.  
- Typically used when running the **main program**, background tasks, OS threads, etc.

---

## ⚡ Handler Mode

- Used when servicing **exceptions** or **interrupts**.  
- Whenever an exception occurs, the processor **automatically switches** from Thread Mode → Handler Mode.  
- Always runs in **Privileged mode**, giving full access to:
  - System registers  
  - Memory regions  
  - OS kernel operations  
- Examples of code that runs in Handler Mode:
  - SysTick Handler  
  - Interrupt Service Routines (ISRs)  
  - HardFault Handler  
  - SVC (Supervisor Call) Handler  

---
