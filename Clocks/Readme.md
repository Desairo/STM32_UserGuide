# Clocks of Microcontroller
Microcontroller is a digital circuitary synchronous with clock.Microcontroller needs clock to operate.  
There are three different clock sources present:-  
1)HSE Oscillator Clock(Crystal Oscillator which is connected externally).  
2)HSI Oscillator Clock(RC Oscillator which is internally connected).  
3)Main PLL Clock(Phase Locked Loop which is internal to microcontroller).  

---

# HSI Clock
1)It is default clock.This internal clocks are not precise and stable.  
2)HSI is an internal RC oscillator built inside the microcontroller.  
3)Here no any external components are required and basically used for low-cost designs.  

---

# HSE Clock
1)HSE is an external crystal oscillator or an external clock signal connected to the microcontroller pins.  
2)Compared to HSI it is very accurate and stable but is of higher cost.  
3)Useful in real time applications and communication-based systems.  

---

# PLL
1)The PLL(Phase-Locked Loop) is a frequency multiplier used in STM32 microcontrollers to generate higher system clock frequencies from a lower-frequency source.  
2)PLL can take input from HSI or HSE.  
3)PLL typically has divider and multiplier to modify the frequencies.  
