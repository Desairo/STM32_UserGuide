# 🟦 PendSV Exception

1) PendSV is **exception number 14** and has a **fully programmable priority level**.  
2) It is triggered by **setting its pending bit** in the *Interrupt Control and State Register (ICSR)*.  
3) Triggering PendSV is a common way for a **preemptive kernel** to request a *context switch*.  
4) In operating systems, the **PendSV handler is always assigned the lowest priority**, because context switching should only happen when no other important interrupt is active.

---

# 🟩 Important PendSV Information

1) PendSV is usually triggered inside a **high-priority exception handler**, but it executes **only after** all higher-priority interrupts are finished.  
2) PendSV always runs **after all ISR processing is complete**.  
3) PendSV helps in **interrupt-noisy environments**, allowing context switching to be delayed until all interrupts finish.  
4) **Context switching** = saving current task context + restoring next task context.  
5) Context switching does **not** happen inside SysTick ISR.  
   SysTick only *requests* a context switch by pended PendSV.  
   The actual save/restore happens inside **PendSV handler**.  
6) SysTick can preempt an ISR **only if SysTick's priority is higher** than that ISR.

---

### 🔄 Task Switching Example
Shift from **Task A → scheduler → Task B**  
<img width="869" height="399" alt="image" src="https://github.com/user-attachments/assets/eb0f5579-7b3a-4ecf-bea6-b6fe9d7e24c5" />

### ⏱️ SysTick Preemption Case  
SysTick will preempt ISR only if its priority is higher.  
<img width="1122" height="648" alt="image" src="https://github.com/user-attachments/assets/8d35a42c-f314-4223-9717-8c052a1fead1" />

---

# 🟧 Use Cases of PendSV

1) **Offloading interrupt processing** to reduce ISR load.  
2) When a high-priority ISR does time-consuming work, lower priority interrupts suffer → responsiveness drops.  
   Using PendSV helps split work into fast + slow parts.

---

# 🟨 Offloading Interrupt Processing

### 🧩 Two-part ISR design:
1) **First Half (Top Half):**  
   - Runs inside ISR  
   - Handles time-critical actions  
   - Sets PendSV pending bit

2) **Second Half (Bottom Half):**  
   - Runs inside **PendSV Handler**  
   - Contains heavy / slow code  
   - Ensures fast ISR and low latency  

<img width="1014" height="544" alt="image" src="https://github.com/user-attachments/assets/2533b4fb-18d1-4cd7-93a2-057eadaafce0" />

---
