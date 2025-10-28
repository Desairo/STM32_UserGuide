## SVC Instruction
1)THUMB ISA instruction cause SVC exception.  
2)In RTOS user task execute SVC instruction with associated argument to make supervisory calls to seek privileged resources from kernel mode.  
3)When in unprivileged mode and if SVC instruction processor mode goes to privileged mode.  
4)SVC instruction always used with number,which can be used to identify request type.  
5)SVC handler executes right after SVC instruction.

---

## Trigger SVC instruction
1)Direct execution of SVC instruction with immediate value.  
SVC #0x04  
2)Set exception pend bit in SHCSR(uncommon method).

---

## How to extract SVC No
1)SVC instruction has number embedded within it reffered to as SVC no.  
2)In SVC handler first fetch opcode of SVC and then extract SVC no.  
3)To get opcode we should have value of PC where user code had interrupted while triggering SVC instruction.  
4)Value of PC where user code had interrupted is stored in satck as a part of execption entry sequence by processor.
