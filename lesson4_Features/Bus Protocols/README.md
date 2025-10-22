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
