## Startup file
1)Resposible for setting up right environment for main user code to run.It runs before main() function and then calls main() function.  
2)In this soem part is target dependent that is processor dependent.Startup code takes care of vector table placement in code memory as required by ARM 
cortex Mx processor.  
3)It also take care of stack reinitialisation.It is responsible for .data, .bss section initialisation in main memory.  
4)Startup file can be created as .c or .s file as assembly file.

---

## Linker scripts
1)It tells merging of different object files.Linker and locator assigns unique address to different section of output by reffering to address information.  
2)It also includes code and data memory address and size information.Linker scripts are written using GNU language.It has extension ".ld".  
3)Linker commands imclude ENTRY,MEMORY,SECTIONS,KEEP,ALIGN,AT,etc.  
4)ENTRY command basically set entry address information in header of .elf file.Debugger uses this information to locate first function to execute.  
5)Linker uses MEMORY command to assign address to merged sections.It helps linker to calculate total code and data memory consumed.  
6)SECTIONS command used to create different output sections in final .elf executable generated.It controls order in which different output sections appear in .elf file.

---

## Location Counter
1)Linker symbol denoted by '.',this symbol is a location counter.Linker automatically updates this symbol with location.  
2)Used to track and define boundaries of various sections.We can keep any specific value while writing linker script.  
3)Location counter should appear in SECTIONS part and it should be incremented by size of the output section.

---

## OpenOCD(On-Chip Debugger)
1)This aims to provide debugging,in-system programming and boundary-scan testing for embedded target devices.It is free and opensource application 
allowing to program,debug and analyze applications using GDB.  
2)It supports various target boards based on different processor architecture.OpenOCD currently supports many types of debug operators which includes 
USB,parallel ports,etc.  
3)GDB debugger allows ARM7,ARM9 to be debugged via GDB portal.

---

## Programming Adaptors
1)This are used to get an access to the debug interface of target with native protocol signaling such as SWD or JTAG since host doesn't support such interfaces.  
2)It does protocol conversion.Debug adapter helps to download and debug the code.  
3)Some advanced debug adapters will also help to capture trace events such as on the fly instruction trace and profiling information.  
4)Poplar examples include SEGGERJ-LINK EDU.

---

## Semihosting
1)It is technique by which we can see printf messeges in openocd console.  
2)Semihosting will work only when OpenOCD is running.Here support from host is required thus OpenOCD works as host here.
