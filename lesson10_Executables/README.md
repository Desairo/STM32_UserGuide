# Bare Metal Executables
A bare metal executable refers to a program that runs directly on hardware — without any operating system in between.
This basically consists of startup code,vector table and low level peripheral drivers.

---

## Cross compilation
1)It is the process in which cross toolchain runs on host machine and creates executables that run different machine.  
2)Toolchain is the collection of binaries which allows us to compile,assemble,link applications.  
3)It also contains binaries which help us to analyze executables.Dissect different sections of executable.

---

## Build Process 
1)Pre-processing stage-here all preprocessing directives will be resolved.Means from here we give main.c file and we will get 
main.i file which is preprocessed file.  
2)Code generation stage-here preprocessed file is being used to create a source file which consist of assembly language code 
which shows processor architectural level mnemonics.  
3)Assembler stage-here assembly level mnemonics are converted to opcodes that is machine code for instructions.  
4)All this is doen by compiler but compiler doesn't save .i and .s files.

<img width="937" height="688" alt="image" src="https://github.com/user-attachments/assets/7b8468a6-1995-4f9b-9e29-418b6c3aaa51" />

---
## Linker Stage
1)Linker is basically used to merge similar section of different objects files to resolve all undefined symbols of different objects.  
2)Locator is a part of linker that takes the help of linker script to understand how you wish to merge different section and assign mentioned address 
to different sections.  
<img width="981" height="496" alt="image" src="https://github.com/user-attachments/assets/8e96f3c2-e437-4c3e-98c1-f719c4361b8a" />

---
## Important points
1)ELF is standard file format for object and executable files.A file format standard describes a way of organising various elements 
of a program in different sections.From this .elf format we can create .bin and .hex files.    
2)Parser are crucial for transforming human readable code or data into format that can be processed efficiently by machine.In program code operates on data.
Instructions are stored in flash memory of microcontroller.Data is stored in main memory.  
3)Data is not stored in flash memory because data conatins variables which may change during runtime.So,it make sense to store read only data in flash.  



