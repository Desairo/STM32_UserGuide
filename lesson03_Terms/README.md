# 🌟 Lesson 3: Important Terminologies for Debugging

STM32 offers several features that help developers monitor and interact with the system while it is running.  
These tools combine hardware and software capabilities to make debugging, tracing, and system optimization  
easier and more efficient in **real time**.

---

## 📌 Trace

1) Refers to the process of monitoring and recording real-time execution running on the microcontroller.  
2) It allows developers to observe the behavior of code without stopping or altering its execution.  
3) Tracing can log specific events, such as when an interrupt is triggered or when a certain function is called.

---

## 📡 SWV (Serial Wire Viewer)

1) SWV allows tracing data in real time while the microcontroller is running.  
2) It is used to track exceptions, interrupts, function calls, etc.  
3) SWV uses the **SWO** pin to output trace data.  
4) SWV outputs *printf*-style debug messages without requiring an additional UART.

---

## 🔧 SWD (Serial Wire Debug)

1) Interface used with the microcontroller for programming, debugging, and monitoring the execution of code.  
2) Uses **SWDIO** and **SWDCLK** pins for communication.  
3) SWD allows setting breakpoints to debug.  
4) It is used to interact with the microcontroller during development.

---

## 🔈 SWO (Serial Wire Output)

1) Communication channel used for outputting data from the microcontroller to the debugging tool.  
2) SWO uses a single pin to transmit data, including real-time information such as *printf*-style debug messages.  
3) It provides advanced features like real-time tracing. It is an optional feature.

---

## 🧩 ITM (Instrumentation Trace Macrocell)

1) Commonly used for basic debugging tasks where developers need to output debug messages.  
2) It tracks software events and monitors variable values without significantly affecting microcontroller performance.  
3) It provides a simple and low-overhead way to insert *printf*-like debug statements into code.

