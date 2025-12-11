# ⚠️ Exceptions  
Anything that disturbs the normal execution of a program by changing the processor’s operational mode.

---

## Types of Exceptions

### 1) System Exceptions  
- Generated internally by the processor.  
- Total **15 system exceptions** exist.

### 2) Interrupts  
- Generated from the external world.  
- Total **240 interrupts** exist.

---

# 🧩 System Exceptions

1. Out of 15 exceptions, **9 are implemented** and **6 are reserved**.  
2. Exception number **16** is the first interrupt request (**IRQ1**).  
3. System exceptions include:  
   - Reset  
   - NMI  
   - HardFault  
   - MemManage  
   - BusFault  
   - UsageFault  
   - (Reserved)  
   - SVC Call  
   - PendSV  
   - SysTick  
   - Interrupts  

---

## 🔍 Description of Key System Exceptions

1. **NMI (Non-Maskable Interrupt)**  
   - Triggered by a peripheral or software.  
   - Cannot be disabled; highest priority.  
   - Used for emergency conditions such as hardware failures.

2. **HardFault**  
   - Occurs when an error happens during exception processing.  
   - Example: Invalid T-bit (T = 0).

3. **Interrupt Enable Requirement**  
   - Interrupts must be enabled in both **NVIC** and the **peripheral** generating them.  
   - Otherwise, exceptions may cause a **HardFault**.

4. **MemManage Fault**  
   - Triggered when the processor accesses a protected or restricted memory region.

5. **Usage Fault**  
   - Caused by undefined instructions, unaligned access, invalid state, etc.

6. **SVC (Supervisor Call)**  
   - Used by **unprivileged code** to request services from the OS kernel.  
   - Each SVC instruction includes a **service number**.

7. **PendSV**  
   - Used for **context switching** when no other exception is active.  
   - Typically used by RTOS kernels.

---

# 🧰 System Exception Control Registers

1. These registers control core functionality such as NVIC, FPU, MPU, etc.  
2. **SCB (System Control Block)**  
   - Provides system-level information and control.  
   - Includes fault handler enable bits, fault status, sleep/wake control.

3. **System Handler Priority Registers**  
   - Used to configure priority levels of system exceptions.

4. **SHCSR (System Handler Control and State Register)**  
   - Enables system handlers like BusFault, MemManage fault.  
   - Shows pending status of system exceptions.

---

# 🔔 NVIC (Nested Vectored Interrupt Controller)

1. A core peripheral of the Cortex processor used to manage all **240 interrupts**.  
2. Can enable, disable, or pend interrupts and read active interrupt status.  
3. Configures priority and priority grouping.  
   - “Nested” because a higher-priority interrupt can preempt a lower one.  
4. Interrupt signals originate from vendor-specific on-chip peripherals.

---

# 📑 Important NVIC Registers

- **ISER (Interrupt Set Enable Register)**  
  - 8 registers  
  - Used to **enable** interrupts (cannot disable).

- **ICER (Interrupt Clear Enable Register)**  
  - Used to **disable** interrupts.

- **ISPR (Interrupt Set Pending Register)**  
  - Sets an interrupt to the **pending** state.

- **ICPR (Interrupt Clear Pending Register)**  
  - Clears the pending state.

- **IABR (Interrupt Active Bit Register)**  
  - Shows whether an interrupt is currently being serviced.
