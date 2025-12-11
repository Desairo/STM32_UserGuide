# 🔄 Reset Sequence of Cortex Processor

1. The processor first reads the value at **0x0000_0000** into the **MSP (Main Stack Pointer)**.  
   This initializes the stack pointer.

2. Then it reads the value at **0x0000_0004** into the **PC (Program Counter)**.  
   This value is the address of the **Reset Handler**.

3. The PC jumps to the **Reset Handler**, which performs all required initializations  
   and then calls the **main()** function.

---

# 🛡️ Access Levels of the Processor

1. It is restricted to switch from **unprivileged mode** to **privileged or handler mode**  
   because this could create security risks. Application code (usually unprivileged)  
   should not control system-level operations.

2. To make **Thread Mode** unprivileged, modify the **CONTROL register** and set **nPRIV = 1**.

3. User tasks should not alter system-level processor states or trigger interrupts directly.  
   If unprivileged code needs privileged services, it triggers a **system call**,  
   which is handled by kernel (privileged) code.

4. Once an interrupt is triggered, the processor automatically switches to **Handler Mode**  
   (which is privileged), and after completing the ISR it returns to **Thread Mode**.

---

# 🅣 Importance of the T Bit

1. ARM uses **32-bit wide instructions**, offering high performance.  
   The **THUMB instruction set** uses **16-bit wide instructions**, which leads to  
   more compact code — useful for reduced memory usage.

2. The **T bit** indicates the instruction mode:  
   - **T = 0 → ARM instruction**  
   - **T = 1 → THUMB instruction**  
   Cortex processors typically operate in **THUMB mode**.

3. Whenever a value or address is loaded into the PC, **bit 0** of that value is loaded into the **T bit**.  
   Therefore, any address loaded into the PC **must have bit 0 = 1**, meaning the address must be **odd**.

4. If bit 0 is **0**, the processor detects a **HardFault**.  
   The compiler automatically adjusts addresses to ensure bit 0 is set correctly.
