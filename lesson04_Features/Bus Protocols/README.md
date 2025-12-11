# 🚍 Bus Protocols and Bus Interfaces

In Cortex processors, bus interfaces are based on **AMBA (Advanced Microcontroller Bus Architecture)**.  
This specification, designed by **ARM**, defines the standards for **on-chip communication inside SoCs (System on Chip)**.  
It supports several bus protocols including:

- **AHB (AMBA High-performance Bus)**
- **APB (AMBA Peripheral Bus)**

---

# ⚡ AHB vs APB

1. **AHB** is used for main bus interfaces.  
2. **APB** is used for **PPB (Private Peripheral Bus)** access and some on-chip peripheral access using the **AHB-APB bridge**.  
3. **AHB** is mainly used for **high-speed communication**, especially with peripherals demanding high operational speed.  
4. **APB** is used for **low-speed communication** compared to AHB. Most peripherals that *don’t require* high speed are connected to this bus.

---

### 🧠 I-Code & D-Code Access

- **I-Code** → Processor fetches instruction from vector memory.  
- **D-Code** → It accesses data from the code region.  

The processor communicates with flash through the **I-Bus** and **D-Bus**.  
All **D-Bus, I-Bus, and S-Bus** are connected to the **Bus Matrix**.

---

## 🕸️ Bus Matrix

The **Bus Matrix** is the on-chip interconnect fabric connecting **bus masters** to **bus slaves**.  
Processor access is controlled by the **arbiter**.  
Multiple masters can access different slaves simultaneously (based on arbitration).

---

### 🧩 1) Bus Master
- Includes **Processor, DMA, USB**, etc.  
- A bus master **controls the bus** and initiates communication with devices connected to it.  
- It starts and manages data transfers.  
- Arbitration is required to decide **which master gets bus control** at a given time to prevent conflicts.

---

### 🗃️ 2) Bus Slave
- Includes **Flash, SRAM, GPIO, UART, SPI, ADC, Timers**, and other peripherals.  
- A bus slave **does not initiate** communication. It only responds to the master.  
- Bus matrix ensures **only one master accesses a slave at a time** to avoid corruption.

---

### 🎯 3) Bit-Banding
- It provides the ability to **address a single bit** in memory.  
- Every bit in a word gets its **own alias address**.  
- Allows modifying one bit without affecting other bits in the same word.  


Formula:   
alias_address=alias_base+(32*(bit_band_memory_address-bit_band_base))+bit*4  
Where:  
`bit_band_memory_address = memory address of the bit to be modified`

---

## 🔌 Bus Interfaces

Processor and peripherals communicate via **bus interfaces**, which include:

1. **I-Bus** → Fetches instructions from flash  
2. **D-Bus** → Accesses data  
3. **S-Bus** → Handles system-level operations  

📦 **Constant data** is stored in **Flash**, while **variables** are stored in **SRAM**.


