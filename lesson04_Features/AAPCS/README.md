# 📘 AAPCS (ARM Architecture Procedure Call Standard)

AAPCS defines the **procedure call standard** used in the ABI (Application Binary Interface) for ARM architecture.  
It ensures that functions written in C, assembly, or different modules can **interoperate seamlessly**.

It specifies the rules followed when:
- A function **calls** another function  
- A function **is called**  
- Data is passed (arguments + return values)  
- Registers and stack must be **preserved**  

---

## 🎯 Key Responsibilities Defined by AAPCS

### 1️⃣ Caller Responsibilities
- Must prepare the program state so that the callee can begin executing properly.
- Caller must **save any registers** it needs later *if the callee is allowed to overwrite them*.

### 2️⃣ Callee Responsibilities
- Must preserve certain registers and restore them before exiting.
- Must return results in the correct registers defined by the AAPCS.

### 3️⃣ Rights of the Callee
- Can modify *only a specific set of registers* without saving them.
- Must respect callee-saved register rules.

### 4️⃣ Compiler Compliance
- The C compiler follows AAPCS while generating function call/return instructions.
- Ensures consistent calling convention across all modules.

---

# 🧮 Register Usage in AAPCS

### ✔️ **Caller-Saved (Volatile) Registers**  
Registers the *caller must save* if it wants to preserve their values:

| Register | Purpose |
|---------|---------|
| **R0–R3** | Used to pass function arguments |
| **R0–R1** | Used by callee to return values |
| **R0–R3, R12, LR** | Scratch registers (caller must save) |

- Caller uses **R0–R3** for arguments  
- If more than 4 arguments → **remaining arguments go on the stack**

### ✔️ **Callee-Saved (Non-Volatile) Registers**
Registers the **callee must preserve**:

| Register |
|----------|
| **R4–R11** |

- Callee must save R4–R11 on its own stack frame (if it modifies them)
- Must restore them before returning

---

# 📥 Stack Activities During Interrupts

Interrupts behave differently from normal function calls.

### 🌩️ 1️⃣ Interrupts have no caller  
- They are invoked **by hardware**, not by a function call  
- So **AAPCS rules do NOT apply** to interrupts

### 🧷 2️⃣ Automatic Stacking by Hardware  
When an interrupt occurs, the Cortex-M hardware **automatically pushes**:

- R0  
- R1  
- R2  
- R3  
- R12  
- LR  
- PC  
- xPSR  

These registers are saved **without software involvement**.

### 🔄 3️⃣ Restoring at Exception Exit  
Before returning from the interrupt handler, hardware automatically **restores** all stacked registers so the program continues exactly where it left off.

---

# 📝 Summary

- AAPCS ensures consistent calling conventions for function calls.  
- Caller uses R0–R3 for arguments; callee must preserve R4–R11.  
- Interrupts **do not use** AAPCS because they are triggered by hardware.  
- Cortex-M hardware automatically saves/restores context during exceptions.

---

