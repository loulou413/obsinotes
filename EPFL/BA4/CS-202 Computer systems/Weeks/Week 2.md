---
Week: 2
Themes: 
Lecture1: true
Lecture2: false
Exercises: false
---

  

# Notes

  

## Lecture 1
### L03.1: Isolation and Protection
#### CPU virtualization: Efficient process execution
Goal: Give each process the illusion of exclusive CPU access
Reality: The CPU is a shared resource among all processes
We can time share or space share 
CPU: time sharing, alternate between tasks 
• Memory: space sharing (more later)
• Disk: space sharing (more later)
### L03.2: Limited Direct Execution
Limited direct execution enables programs to execute as fast as possible with some restriction
Direct execution run the program directly on the CPU without  without any restrictions

![[Pasted image 20240226134328.png]]

Issues :
- How does the OS ensure that a process does not execute/run a privileged code, while running it efficiently?
- How does the OS stop running a process and switch to another one, which is required for virtualizing the CPU?
Dual mode comes in : 

| User mode                                 | Kernel mode                                     |
| ----------------------------------------- | ----------------------------------------------- |
| User process executes                     | Operating system kernel mode executes           |
| CPU can execute only regular instructions | Can execute regular and privileged instructions |
Common examples of privileged instructions: 
- Change the MMU register that controls page tables (mov %cr3 on x86-64) 
-  Enable or disable interrupts 
-  Access I/O devices 
-  Change privilege levels
When the CPU attempts to execute a privileged instruction from user mode: 
-  The instruction does not execute 
-  The instruction traps (#General protection fault on x86)
-  The operating system takes control
### L03.3: System calls
##### ***How can a process request (from the OS) for operations that are only possible in the kernel mode (example: IO requests)***
System calls transfer execution to the OS, meanwhile the execution of the process is suspended
![[Pasted image 20240226135603.png]]

A process executes a special trap instruction ---> CPU jumps in kernel mode and raises  the privilege lvl ---> privileged operations can now be done. 
Trap is a signal raised by a process instructing the OS to perform some functionality immediately
- When finished, the OS calls a special return-from-trap instruction
- Returns to the calling process and lowers the privilege level at the same time
- Now, privileged operations cannot be performed
### L03.4: Traps and Interrupts


  

## Lecture 2

