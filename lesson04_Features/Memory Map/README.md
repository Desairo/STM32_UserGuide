# 🧭 Memory Map of the Cortex Processor

The **memory map** defines how different memories and peripheral registers are arranged in the processor’s addressable space.  
This layout depends on the width of the **address bus**.

---

## 📌 Basics

1. **Code memory** → Stores instructions.  
2. **Data memory** → Stores variables and runtime data.  
3. The **system bus** uses:  
   - 32-bit address bus  
   - 32-bit data bus  
4. When the CPU needs a value, it places the register's address on the address bus.  
   - If a peripheral/register matches the address, it unlocks and places its value on the data bus.  
5. Total addressable range: **0x0000_0000 → 0xFFFF_FFFF (4 GB)**.

---

# 🗂 Memory Regions

## 🧩 1. Code Region  
- **Range:** `0x0000_0000 → 0x1FFF_FFFF`  
- Contains **embedded Flash**, ROM, EEPROM, and other executable memory.  
- After reset, the processor fetches the **vector table** from this region.

---

## 🧩 2. SRAM Region  
- **Range:** `0x2000_0000 → 0x3FFF_FFFF`  
- Comes immediately after the code region.  
- Contains on-chip SRAM.  
- **First 1 MB** is **bit-addressable** (important for bit-banding feature).

---

## 🧩 3. Peripheral Region  
- **Size:** 512 MB  
- Used for **on-chip peripheral registers** like GPIO, UART, SPI, ADC, timers.  
- **First 1 MB is bit-addressable**.  
- Marked as **Execute Never (XN)** — executing code here triggers a fault.  
- This avoids **code injection attacks** or accidental execution.

---

## 🧩 4. External RAM Region  
- Used for external or large memory devices.  
- Code **can** be executed here.  
- Very useful for applications like **graphics**, frame buffers, and large data handling.

---

## 🧩 5. External Device Region  
- Designed for external devices or shared memory.  
- Marked **execute-never** (XN).  
- Not intended for running code.

---

## 🧩 6. Private Peripheral Bus (PPB) Region  
- Contains **processor-specific** peripheral registers such as:  
  - NVIC  
  - SysTick  
  - System Control Block (SCB)  
  - Debug components  
- Also an **execute-never** region.

