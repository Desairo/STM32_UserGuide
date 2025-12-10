# Lesson 1: Introduction to Embedded Systems

Embedded systems are specialized computer systems designed to perform a specific task.  
They are a combination of **hardware + software**, created for a dedicated function.  
Examples: washing machines, drones, and smartwatches.

---

## 🧠 Embedded Processor – The Brain of the System

An embedded processor consists of a control unit and an execution unit.  
It can be a **microcontroller** or a **microprocessor**, depending on the complexity of the system.

---

## Microcontroller vs Microprocessor

| Feature       | Microcontroller            | Microprocessor            |
|---------------|----------------------------|---------------------------|
| Memory        | Built-in RAM + Flash       | Needs external memory     |
| Power usage   | Low                        | Higher                    |
| Cost          | Cheaper                    | More expensive            |
| Examples      | STM32, Arduino             | Intel i5, ARM Cortex-A    |

---

## Why ARM Cortex?

ARM Cortex-M microcontrollers are popular for embedded systems because:  
- Low power consumption  
- Uses THUMB instruction set that gives better code density  
- Rich peripheral set (UART, SPI, I2C, ADC, Timers)  
- Widely supported by tools  

---

## Extra Points

1) ARM releases the Technical Reference Manual (TRM) as documentation of the processor they use.  
2) Every processor in ARM is created with the processor core and specific peripherals surrounding it.  
   Peripherals include NVIC, MPU, AHB, ITM, Bus Matrix, etc.  
3) The processor interacts with the outer world through three bus interfaces: **ICode, DCode, and System Bus**.  
4) To get information related to a specific microcontroller—pin configuration, initializations, power requirements, etc.—it is recommended to check the **datasheet** and **reference manual**.

---

## IDE

IDE stands for **Integrated Development Environment**, which contains essential tools to develop, compile,  
link, and debug the code.  
For STM32, **STM32CubeIDE** is used. It is an Eclipse-based IDE with STM32-specific customization.  
You can download it from the official STM32 website.

---

Now that you have understood the basics, in the next lesson, we will dive into the **STM32 hardware overview** and get ready to create our first **Hello World** project.
