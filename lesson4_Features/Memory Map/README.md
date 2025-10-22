# Memory map of the processor

Memory map explains mapping of different peripheral registers and memories in processor 
addressable memory location range.This range depends upon size of the address bus.

---

1)Code memory consist of instructions.  
2)Data memory consist of data.  
3)System bus has 32 bit address channel and 32 bit data channel.  
4)For fetching data of any register CPU produces address of that register and when address matches with that
register it will be unlocked and value released on data bus.At the end it will be stored in memory.  
5)Memory range is from 0x0000_0000 to 0xFFFF_FFFF.

---

## Code Region
1)This span from 0x0000_0000 to 0x1FFF_FFFF.  
2)Code memories include embedded flash,ROM,EEPROM,etc.  
3)After reset processor by default fetches vector table information from this region.

---

## SRAM 
1)This span from 0x2000_0000 to 0x3FFF_FFFF.  
2)This part present just after the code region.  
3)It has mostly on-chip SRAM.First 1MB is bit addressable.

---

## Peripheral region
1)It is of size 512MB with mostly used for on-chip peripherals.  
2)First 1MB is bit addressable.It is execute never region.Trying to execute code from this region will trigger fault exception.  
3)Processor peripheral registers will not fall in this category.It basically prevents processor from code injection attack.

---

## Externel RAM 
1)Region intended for either on-chip or off-chip memory.We can execute code in this region.  
2)In case of projects which are graphics related its suitable to use this memory.

---

## Externel device region
Intended for externel devices or shared memory.This is execute never region.

---

## Private peripheral bus region
Here we get processor peripheral register such as NVIC,System Timer,System control block.This is execute never region.
