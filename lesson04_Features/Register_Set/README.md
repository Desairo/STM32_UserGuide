# 🧩 Register Set of the Microcontroller

Registers are small, fast storage elements inside the processor used to hold data, addresses, and control information.  
They are accessed extremely quickly during instruction execution.

---

## 🧮 Core Registers

### 1. **General Purpose Registers (R0–R12)**
- Total **13 registers** used for general computation.
- Each is **32-bit wide**.
- Used to store temporary variables, function parameters, intermediate results, etc.

### 2. **Stack Pointer (R13 / SP)**
- Holds the current **top of the stack address**.
- Cortex-M uses two stack pointers:
  - **MSP (Main Stack Pointer)** → used during reset, exception handling, and privileged tasks.
  - **PSP (Process Stack Pointer)** → used for application-level / RTOS tasks.

### 3. **Link Register (R14 / LR)**
- Stores the **return address** for:
  - Function calls  
  - Subroutines  
  - Exceptions  
- Special LR values determine how exceptions return.

### 4. **Program Counter (R15 / PC)**
- Holds the address of the **next instruction** to be executed.
- Updates automatically as instructions execute.

---

## 🏷️ Special Registers (PSR)

### 1. **Program Status Register (PSR)**  
The PSR is divided into 3 sub-registers:

#### a) APSR — *Application Program Status Register*
- Contains all **conditional flags**:
  - N (Negative)  
  - Z (Zero)  
  - C (Carry)  
  - V (Overflow)  

#### b) IPSR — *Interrupt Program Status Register*
- Contains the **ISR number** of the currently running exception/interrupt.
- Helps identify which interrupt is being serviced.

#### c) EPSR — *Execution Program Status Register*
- Contains the **T-bit**, which indicates the instruction set:
  - `1 = THUMB`  
  - `0 = ARM` (not allowed on Cortex-M)
- Cortex-M always requires T-bit = 1.

---

## 🚫 Non-Memory-Mapped Registers

- Include **core registers (R0–R15, PSR, etc.)**.
- **Do not have unique memory addresses**.
- Not accessible using C pointers or memory dereferencing.
- Can only be accessed via:
  - Assembly instructions  
  - Compiler intrinsics  

---

## 🗂️ Memory-Mapped Registers

- These registers **do have fixed addresses** in the processor’s memory map.
- Can be accessed in C using pointers or CMSIS macros.

### Examples:

#### 1. **Processor-specific peripherals**
- NVIC (Interrupt controller)  
- MPU (Memory Protection Unit)  
- System Control Block (SCB)  
- Debug registers  

#### 2. **Microcontroller-specific peripherals**
- GPIO  
- UART  
- SPI  
- I2C  
- CAN  
- Timers (TIMx)  
- RTC  

These registers allow software to configure and control hardware modules.

---
