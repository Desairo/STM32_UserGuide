# Programming MCU peripheral interrupt
1)Use MCU vector table to identify IRQ no of peripheral.Then program processor register to enable that IRQ.  
2)Configure peripheral through its peripheral configuration register.When IRQ issued on IRQ line it will be first pended in pending register.  
3)NVIC will allow IRQ handler to execute the new interrupt only if its priority is greater than current executing interrupt.

---

## How interrupt is issued

<img width="706" height="505" alt="image" src="https://github.com/user-attachments/assets/2789116b-22d7-4bb9-af87-a034a79406fe" />

---

## Interrpt Priority
1)Priority means urgency and priority value is measure of urgency.Lesser the priority value higher the priority.  
2)How many different priority levels are there in cortex processor depends upon intrrupt priority register implementation.  
3)This priority register is part of NVIC register set.There are total 60 interrupt priority register.It provides 8 bit priority field for each interrupt.Each register holds 
four priority fields.  
4)In case of system exception go for system control block and there go to system handler priority register.  
5)Sub Priority=Two interrupts with same preempt priority value occur at same time.In this case exception with high sub priority will be handled first.  
6)Preempt Priority=When processor is running interrupt handler and another interrupt appears then preempt priority values will be compared and high priority 
will be allowed.  
7)When both sub and preempt priority are same,interrupt with lowest IRQ no will be allowed first.  
8)If pending bit is not set interrupt will not be triggered.When interrupt is triggered we enter into Interrupt Hanlder.
