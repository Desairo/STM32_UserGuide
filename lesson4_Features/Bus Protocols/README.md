# Bus protocols and Bus interfaces
In cortex bus interfaces are based on Advanced Microcontroller Bus Architecture(AMBA).It is soecification designed 
by ARM which governs standard for on-chip communication inside SoC(System On Chip).It supports several bus protocols which
include AHB(AMBA High performance Bus) and APB(AMBA Peripheral Bus).

---

# AHB and APB
1)AHB is used for main bus interfaces.  
2)APB is used for PPB(Private Peripheral Bus) access and some on-chip peripheral access using AHB-APB bridge.  
3)AHB majorly used for high speed communication with peripheral demand high operation speed.  
4)APB used for low-speed communication comapred to AHB.Most of peripherals which don't require high operation speed 
are connected to this bus.

---

I-Code=Processor fetches instruction from vector memory.  
D-Code=It will access data from code region.  
Processor communicate with flash through D-Bus and I-Bus.All D-Bus,I-Bus,S-Bus are connected to bus matrix.

---

## Bus Matrix
Bus matrix is the on-chip interconnect fabric that connects bus masters to bus slaves.Processor access can be given and taken care by the 
arbiter.To access different slaves multiple masters are present.  

1)Bus Master:-  
a)This includes processor,DMA,USB,etc.  
b)Bus master is the one who take control over the bus and initiate communication with other devices connected to bus.It is responsible for starting and 
managing data transfer.  
c)Arbitration mechanism is needed to decide which master can control the bus at any given time,preventing conflicts between so many masters.  

2)Bus Slave:-
a)This includes memory blocks (Flash, SRAM) and peripherals (GPIO, UART, SPI, ADC, Timers, etc.) that are connected to the bus.  
b)A bus slave does not initiate communication.It only responds to requests made by a bus master.  
c)The bus matrix ensures that only one master at a time can access a given slave to avoid data corruption.  

3)Bit Banding:-  
a)It is capability to address single bit of memory address.This feature is optional.  
b)By using bit banding we can address individual bits.Every bit position has its own address.  
c)Alias address for each bit is different.This allows single bit in a word to be addressed and modified without 
affecting other bits in word.  

alias_address=alias_base+(32*(bit_band_memory_address-bit_band_base))+bit*4  
bit_band_memory_address=memory address of which bit we are going to change.
