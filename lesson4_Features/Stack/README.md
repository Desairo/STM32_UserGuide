# Stack Memory
1)It is part of memory reserved for temporary storage of data during function call,interrupts,etc.  
2)It follow LIFO(Last In First Out) order.It can be accessed using PUSH and POP instructions or memory manipulation instructions.  
3)It is traced using stack pointer.  

---

<img width="807" height="277" alt="image" src="https://github.com/user-attachments/assets/14262631-f20b-4c9e-8742-86a417515359" />
1)SRAM is of 128KB where RAM starts at left end and end at right side.  
2)Global data region is utilized when program contains global data and static load variables.  
3)Heap memory will be used for dynamic memory allocation.  
4)Stack memory will be utilized for temporary storage of data or stack frames.

---

## Stack consumption model
1)FA(Full Ascending)  
SP is ascending with increasing address values.SP points to the last stored (full) location.

2)FD(Full Descending)  
Here there is decrement in the stack pointer so initialise SP with higher memory address.

3)EA(Empty Ascending)  
Stack grows toward higher memory addresses, and SP points to the next empty location where the next item will be stored.

4)ED(Empty Descending)  
Stack grows toward lower memory addresses, and SP points to the next empty location where the next item will be stored.

In ARM cortex FD model is being used.

---

Stack Placement:-  
<img width="548" height="527" alt="image" src="https://github.com/user-attachments/assets/b825df85-278c-4f3e-a92c-602afc9f9560" />

---





