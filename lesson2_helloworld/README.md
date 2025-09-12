# Lesson 1: Introduction to STM32

STM32 is a family of 32-bit ARM Cortex-M microcontrollers which is developed by STMicroelectronics.
They are widely used in industry, research, and even projects because of their performance, low power consumption, and rich peripherals.

---

Because of the diverse application needs STM32 introduced different families from low power devices to high 
performance system.

| Series    | Core          | Focus                         | 
| --------- | ------------- | ----------------------------- | 
| **F0**    | Cortex-M0     | Entry-level MCU               | 
| **F1**    | Cortex-M3     | General purpose,easy to use   | 
| **F4**    | Cortex-M4     | Cost effective and efficient  |
| **L0/L4** | Cortex-M0+/M4 | Ultra-low power               | 
| **H7**    | Cortex-M7     | High-end, very powerful       | 

---

## STM32F407 Discovery Board

Core: ARM Cortex-M4(32 bit)  
Memory: 192 KB SRAM, 1 MB Flash  
Peripherals: GPIO, UART, SPI, I2C, ADC, DAC, Timers, USB OTG, CAN, Ethernet  
power supply: 3V and 5V  
On-board ST-LINK/V2-A debugger  
Support IDE STM32CubeIDE

---

## Steps to execute program in IDE
1)Write code in STM32CubeIDE.  
2)Compile into a binary/hex file.  
3)Flash the program into the microcontroller using ST-Link.  
4)We can run and debug code directly on board.

---

## IDE
