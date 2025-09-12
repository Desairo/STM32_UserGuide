# Lesson 1: Introduction to Embedded Systems

Embedded systems are specialized computer systems designed to perform specific task.
It is combination of **hardware + software** designed for a dedicated function.
Examples:-washing machines, drones and smartwatches.

---

Embedded processor is the brain of the system.It consist of control unit and execution unit.
Embedded processor can be microcontroller or microprocessor depending upon the complexity of 
the system.

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
- Low power consumption.
- Uses THUMB instruction set that gives better code density.
- Rich peripheral set (UART, SPI, I2C, ADC, Timers).  
- Widely supported by tools.

---

## Extra points
1)ARM releases Technical Reference Manual(TRM) as documentation of processor they use.  
2)Every processor in ARM is created with processor core and specific peripherals surrounding it.  
  Peripherals include NVIC,MPU,AHB,ITM,Bus Matrix,etc.  
3)Processor interacts with outer world with three bus interfaces which include ICode,DCode and System Bus.  
4)To get information related to specific microcontroller,pin configuration,initiallisations,power requirements,etc it is 
recommended to check their datasheet and refernece manual.

---

## IDE
IDE stands for Integrated Development Environment that contains all essential tools to develop,compile,
link and debug the code.  
For STM32,STM32CubeIDE is being used.It is eclipse based IDE with STM32 related customization.
We can download this IDE through the official website of STM32.

---

Now that you have understood the basics, in the next lesson we’ll dive into STM32 hardware overview and get ready to create our first Hello World project.

