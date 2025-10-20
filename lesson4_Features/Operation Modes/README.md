# Operation Modes of the Processor

Operation mode basically handles the CPU during privileged or interrupt requests.
There are two important modes in arm cortex processor which includes:-  
1)Thread Mode  
2)Handler Mode

---

## Thread Mode
1)Normal application code will be executed in thread mode.  
2)Processor always start with thread mode making it a normal execution mode
of the processor.  
3)It has either full access to memory and registers during execution or limited access 
for proper functioning.

---

## Handler Mode
1)All the exception handlers or interrupts run under this mode of the processor.  
2)When exception happens processor changes its mode from thread to handler mode.  
3)We can access any resources in this mode and have complete command over the processor.  
4)This is always privileged access mode.
