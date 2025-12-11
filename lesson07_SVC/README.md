# 🧩 SVC (Supervisor Call) Instruction – Clear & Catchy Notes

## 🚀 What is an SVC Instruction?
1) A **THUMB ISA instruction** that triggers an **SVC exception**.  
2) Common in **RTOS**, where user tasks execute SVC with arguments to request **privileged kernel resources**.  
3) When executed in **unprivileged mode**, the processor switches to **privileged mode** inside the SVC handler.  
4) Always used with a **number**, which identifies the request type.  
5) After the SVC instruction executes, the **SVC handler runs immediately**.

---

## 🎯 How to Trigger an SVC Instruction
1) **Direct execution** using an immediate value:  
   `SVC #0x04`  
2) **Setting the exception pend bit** in SHCSR (rarely used method).

---

## 🔍 Extracting the SVC Number
1) Every SVC instruction contains an **embedded number** known as the *SVC number*.  
2) Inside the SVC handler, first **fetch the opcode**, then extract the SVC number.  
3) To fetch the opcode, we need the **PC value where the program was interrupted** when SVC was triggered.  
4) This PC value is automatically stored in the **stack frame** during exception entry by the processor.
