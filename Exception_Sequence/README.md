## Exception Entry
1)Set the pending bit.  
2)Stacking and Vector fetch.  
3)Entry in handler mode and set active bit.  
4)Clears the pending status(processor does it automatically).  
5)Processor mode changed to handler mode.  
6)Hanlder code start executing.  
7)MSP used for any stack operations inside handler.

---

## Exit Sequence
1)In cortex processor the exception return mechanism is triggered using special return address called EXC_RETURN.  
2)EXC_RETURN generated during entry and stored in LR(Link Register).
3)When EXC_RETURN is written to PC it triggers the exception return.  
4)During exception handler entry,value of the return address is not stored in LR as it is done during calling C function.Instead exception mechanism stores 
special value called EXC_RETURN in LR.
