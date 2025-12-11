## 🏁 Startup File

1) Responsible for setting up the correct environment before the `main()` function runs. It executes **before** `main()` and then calls it.  
2) Some parts of the startup code are **processor-dependent**. It handles **vector table placement** in code memory as required by ARM Cortex-Mx processors.  
3) It also takes care of **stack reinitialization** and the initialization of **.data** and **.bss** sections in main memory.  
4) A startup file can be written in **C (.c)** or **Assembly (.s)**.

---

## 🔗 Linker Scripts

1) Linker scripts define **how different object files are merged**. The linker assigns unique memory addresses to each section by referring to address information.  
2) They include **code and data memory address and size details**. Linker scripts use GNU syntax and have the extension **`.ld`**.  
3) Common linker commands include **ENTRY, MEMORY, SECTIONS, KEEP, ALIGN, AT**, etc.  
4) The **ENTRY** command sets the entry address in the `.elf` file header so the debugger knows where execution begins.  
5) The **MEMORY** command helps assign memory regions to merged sections and allows the linker to calculate overall memory usage.  
6) The **SECTIONS** command defines the output sections in the final `.elf` file and controls their order.

---

## 📍 Location Counter

1) The linker symbol **`.` (dot)** represents the **location counter**, which the linker automatically updates.  
2) It is used to define and track **section boundaries**. You can also assign custom values while writing linker scripts.  
3) The location counter must appear inside the **SECTIONS** block and should be incremented by the size of each output section.

---

## 🧪 OpenOCD (On-Chip Debugger)

1) OpenOCD provides **debugging, in-system programming, and boundary-scan testing** for embedded devices. It is free and open-source, and works with GDB for code download, debugging, and analysis.  
2) It supports many boards and processor architectures, along with various debug interfaces like **USB**, **parallel ports**, etc.  
3) Through GDB, OpenOCD can debug processors such as **ARM7, ARM9**, and more.

---

## 🔌 Programming Adapters

1) Used to access the debug interface (SWD or JTAG) of the target device since host machines don’t directly support these protocols.  
2) They perform **protocol conversion** and allow downloading and debugging of code.  
3) Advanced adapters also capture **trace events**, **instruction flow**, and **profiling information**.  
4) Popular example: **SEGGER J-LINK EDU**.

---

## 🖥️ Semihosting

1) A technique that allows `printf`-style messages to appear in the **OpenOCD console**.  
2) Semihosting works only when **OpenOCD is running**, as it requires support from the host — OpenOCD acts as that host.
