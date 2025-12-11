# ⏰ Clocks of Microcontroller  
A microcontroller is a **digital circuitry synchronized with a clock**. It **needs a clock to operate**.  
There are three main clock sources:  
1) **HSE Oscillator Clock** – Crystal oscillator connected externally.  
2) **HSI Oscillator Clock** – RC oscillator built internally.  
3) **Main PLL Clock** – Phase-Locked Loop internal to the microcontroller.  

---

## 🔹 HSI Clock  
1) Default clock. Internal clocks are **less precise and less stable**.  
2) HSI is an **internal RC oscillator** built inside the microcontroller.  
3) **No external components** required; ideal for **low-cost designs**.  

---

## 🔹 HSE Clock  
1) External crystal oscillator or external clock signal connected to microcontroller pins.  
2) **Highly accurate and stable** compared to HSI, but **higher cost**.  
3) Perfect for **real-time applications** and **communication systems**.  

---

## 🔹 PLL (Phase-Locked Loop)  
1) PLL is a **frequency multiplier** used to generate higher system clock frequencies from a lower-frequency source.  
2) Input can come from **HSI or HSE**.  
3) Contains **divider and multiplier circuits** to modify frequencies as needed.  

---

## 🌐 System Clock  
1) Derives clocks for other domains. An **AHB prescaler** divides system clock value for other domain usage.  
2) **HCLK** (High-speed System Clock) drives the **CPU core** and often the **AHB bus** in Cortex-M microcontrollers.  
3) Peripherals connected to **APB1 and APB2** are clocked via HCLK.  

---

## ⚡ Peripheral Clock Configuration  
1) Before using a peripheral, its **clock must be enabled** via its peripheral register.  
2) By default, clocks are **disabled** to save power.  
3) Managed through **RCC register** (**Reset, Clock, and Control**).  

---

## 🛠️ RCC (Reset, Clock, Control)  
1) RCC allows **selection and management of clock sources**, ensuring proper operation.  
2) Can **reset the microcontroller** and provides **prescaler options** to dynamically adjust frequencies.  
3) Enables **runtime clock adjustments** and helps achieve **precise timing**.
