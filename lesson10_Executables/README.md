# 🚀 Bare Metal Executables  
A **bare metal executable** refers to a program that runs **directly on hardware** — with **no operating system** in between.  
It mainly consists of **startup code**, a **vector table**, and **low-level peripheral drivers**.

---

## 🔧 Cross Compilation  
1) It is the process in which a cross toolchain runs on a host machine and creates executables that run on a different machine.  
2) Toolchain is the collection of binaries which allows us to compile, assemble, and link applications.  
3) It also contains binaries which help us analyze executables and dissect different sections of an executable.

---

## 🏗️ Build Process  
1) **Pre-processing stage** — Here all preprocessing directives will be resolved.  
   We give the `main.c` file and get the `main.i` preprocessed file.  
2) **Code generation stage** — The preprocessed file is used to create a source file consisting of assembly language code,  
   which shows processor architectural-level mnemonics.  
3) **Assembler stage** — Assembly-level mnemonics are converted to opcodes (machine code for instructions).  
4) All this is done by the compiler, but the compiler doesn't save `.i` and `.s` files.

<img width="937" height="688" alt="image" src="https://github.com/user-attachments/assets/7b8468a6-1995-4f9b-9e29-418b6c3aaa51" />

---

## 🧩 Linker Stage  
1) Linker is used to merge similar sections of different object files and resolve all undefined symbols of those objects.  
2) Locator is a part of the linker that takes the help of the **linker script** to understand how you wish to merge different sections  
   and assign the mentioned address to those sections.

<img width="981" height="496" alt="image" src="https://github.com/user-attachments/assets/8e96f3c2-e437-4c3e-98c1-f719c4361b8a" />

---

## 📌 Important Points  
1) **ELF** is the standard file format for object and executable files.  
   A file format standard describes a way of organizing various elements of a program into different sections.  
   From this `.elf` format, we can create `.bin` and `.hex` files.  
2) **Parsers** are crucial for transforming human-readable code or data into a format that can be processed efficiently by machines.  
   In a program, code operates on data.  
   Instructions are stored in the **flash memory** of the microcontroller. Data is stored in **main memory**.  
3) Data is *not* stored in flash memory because data contains variables which may change during runtime.  
   So, it makes sense to store **read-only data** in flash.

