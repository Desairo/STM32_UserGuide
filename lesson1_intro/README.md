# 🌟 Lesson 1: Introduction to Embedded Systems

Embedded systems are **specialized computer systems** designed to perform a specific task.  
They are a powerful combination of **hardware + software** created for a dedicated function.  
**Examples:** washing machines, drones, and smartwatches.

---

## 🧠 Embedded Processor – The Brain of Everything

The embedded processor is the **core of the system**, consisting of a control unit and an execution unit.  
Depending on system complexity, the embedded processor can be either a **microcontroller** or a **microprocessor**.

---

## 🔍 Microcontroller vs Microprocessor

| Feature       | Microcontroller            | Microprocessor            |
|---------------|----------------------------|---------------------------|
| Memory        | Built-in RAM + Flash       | Needs external memory     |
| Power usage   | Low                        | Higher                    |
| Cost          | Cheaper                    | More expensive            |
| Examples      | STM32, Arduino             | Intel i5, ARM Cortex-A    |

---

## 🚀 Why ARM Cortex?

ARM Cortex-M microcontrollers are widely used in embedded systems because:

- Low power consumption  
- THUMB instruction set for better code density  
- Rich peripheral set (UART, SPI, I2C, ADC, Timers)  
- Strong tool support and a large global ecosystem  

---

## 📘 Extra Points

1) ARM releases the **Technical Reference Manual (TRM)** as documentation of the processor they use.  
2) Every ARM processor is built with a **processor core** surrounded by specific peripherals such as  
   NVIC, MPU, AHB, ITM, Bus Matrix, etc.  
3) The processor communicates with the outer world using **three bus interfaces**:  
   **ICode**, **DCode**, and **System Bus**.  
4) For microcontroller-specific details — pin configuration, initializations, power requirements, etc. —  
   always refer to the **datasheet** and **reference manual**.

---

## 🛠 IDE

IDE stands for **Integrated Development Environment**, which includes all essential tools to develop, compile,  
link, and debug the code.  
For STM32, **STM32CubeIDE** is commonly used. It is an Eclipse-based IDE with STM32-focused customization.  
You can download it from the official STM32 website.

---

Now that you have understood the basics, in the next lesson we’ll dive into the **STM32 hardware overview**  
and get ready to create our first **Hello World** project.
