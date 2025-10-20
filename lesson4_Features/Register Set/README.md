# Register set of the Microcontroller 

Registers are basically part of microcontroller that is used to store data,manipulate it.
We can access them very fast during execution of instructions.

---

## Core Registers
1)R0-R12 are general purpose registers reside in the core of the processor.
This are 32 bit wide.  
2)R13 is a satck pointer(SP) consist of two main pointers.PSP(processor SP) and MSP(Main SP).  
3)R14 is a link register.This stores return information for subroutines,fucntion calls and exceptions.  
4)R15 is a Program Counter(PC).

---

## Special Registers
1)Program Status Register(PSR):-  
a)Application Program Status Register(APSR) contains all the conditional flags in it.  
b)Interrupt Program Status Register(IPSR) contsins ISR_NUMBER of the current interrupt service.ISR_NUMBER tells which interrupt is going
to be executed.  
c)Execution Program Status Register(EPSR) important to understand about T bit.If T bit is set it tells that next instruction is from 
THUMB ISA otherwise it is ARM ISA.

---

## Non Memory mapped Registers
1)All abive registers are of this type becuase they don't have unique address to access them.  
2)This registers are not part of the processor memory map.  
3)This can't access registers in C program using address dereferencing.Only assembly language used to access these registers.

---

## Memory mapped Registers
1)They have unique address associated with them and we can access them via C program.  
2)All the processor specific peripherals are part of this registers.This includes NVIC,MPU,DEBUG,etc.  
3)All the microcontroller specific peripherals are also part of this tyep of registers.This includes RTC,TIMER,I2C,CAN,etc.


