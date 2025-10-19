# Lesson 3: Important Terminologies

Some features in STM32 are designed to make development easier 
and more efficient. They combine hardware and software to provide a 
way to observe, interact with, and optimize the system in real time.

---

## Trace
1)Refers to the process of monitoring and recording real time execution of 
running on the microcontroller.  
2)It allows developers to observe behavior of a code without stopping or altering
its execution.  
3)tracing can log specific events,such as when an interrupt is triggured or when a 
certain function is called.

## SWV(Serila Wire Viewer)
1)SWV allows to trace data in real time when microcontroller is running.  
2)It is used to track exceptions,interrupts,function calls,etc.  
3)SWV uses SWO pin to output trace data.  
4)SWV outputs printf style debug messeges without additional UART.  

## SWD(Serial Wire Debug)
1)Interface with microcontroller for programming,debugging,monitoring
execution of code.  
2)SWDIO and SWDCLK used in this for communication.  
3)SWD sets breakpoints to debug.  
4)It is used to interact with microcontroller during development.  

## SWO(Serial Wire Output)
1)Communication channel used for outputting data from microcontroller to
debugging tool.  
2)SWO uses single pin to output data.SWO used to transmit real time data 
such as printf style debugging messeges.  
3)It gives advanced features like real time tracing.Its an optional feature.

## ITM(Instrumentation Trace Macrocell)
1)Commonly used for basic debugging tasks where developers need to output debug 
messeges.  
2)It tracks software events,monitor variable values without significantly affecting 
performance of microcontroller.  
3)It provides simple and low overhead way to insert printf like debug statements in code.  



