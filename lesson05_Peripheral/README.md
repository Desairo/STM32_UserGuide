# ⚡ Programming MCU Peripheral Interrupts

1) Use the **MCU vector table** to identify the IRQ number of a peripheral.  
   Then configure **processor registers** to enable that specific IRQ.  
2) Configure the peripheral using its **peripheral configuration registers**.  
   When an IRQ is generated on the IRQ line, it is first **pended** in the pending register.  
3) The **NVIC** will allow the IRQ handler to execute *only if* its priority is higher  
   than the currently executing interrupt.

---

## 🔔 How an Interrupt Is Issued
 
<img width="706" height="505" alt="image" src="https://github.com/user-attachments/assets/2789116b-22d7-4bb9-af87-a034a79406fe" />

---

# 🎚️ Interrupt Priority

1) **Priority = urgency** → *Lower priority value = higher priority*.  
2) The number of available priority levels depends on the Cortex processor’s  
   implementation of the **Interrupt Priority Register**.  
3) The priority register is part of the **NVIC** and consists of **60 interrupt  
   priority registers**, each providing an **8-bit priority field** per interrupt.  
   One register contains **four 8-bit priority fields**.  
4) For system exceptions, priority settings are located in the **System Control Block  
   (SCB)** under the **System Handler Priority Registers**.  
5) **Sub Priority:**  
   If two interrupts with the same preempt priority occur simultaneously,  
   the one with the **higher sub-priority** is serviced first.  
6) **Preempt Priority:**  
   If the CPU is already executing an interrupt handler and a new interrupt arrives,  
   the one with the **higher preempt priority** will preempt the current one.  
7) If both **preempt** and **sub priority** are the same, the interrupt with the  
   **lowest IRQ number** gets serviced first.  
8) If the **pending bit** is not set, the interrupt will not be triggered.  
   Once triggered, execution enters the **Interrupt Handler**.

---

