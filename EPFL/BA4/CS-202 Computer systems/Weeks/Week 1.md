---
Week: 1
Themes:
  - Intro
  - Role of OS
  - Process
Lecture1: true
Lecture2: true
Exercises: false
---

  

# Notes

  


#### Bootcamp C
#### video 1

~~~c
#include <libraire>

déclaration de fonctions

int main(void){
corps du programme principal
return un int;
}
~~~~
cmd gcc hello.c -0 hello
#### video 2
Une variable est caractérisée par : 
 son type, son identificateur, sa valeur (définie lors de l'initialisation puis modifiée ou non)

types élémentaires : int double char
~~~~c
int val = 2; 
double const pi = 3.14
i=j+3;


~~~~
const : "read-only"

types avancés :
long, short, unsigned
ex : 
~~~~terminal
unsigned long in nb-etoiles
~~~~

depuis C99 : long long, double complex, bool, int8_t
~~~C
for(int i=0, s = 0; i < 5; s+=, i++){}
from l to r 
~~~

ne jms utiliser de break


#### video 5 
ne pas faire de copier coller :
fonctions  :
prototypage : 
~~~~
double moyenne(double x, double y);
~~~~
ou simplement definition de la fonction.  

sans argument :
~~~~
Type f(void);
~~~~~

passage par référence : 
~~~~
void f(int* x){
*x = *x + 1;
printf("x=%d", *x)
}
~~~~

Pas de surcharge en C ! 

Remarque : ++x , x++ :

|  | Fait | Vaut |
| ---- | ---- | ---- |
| x++ | incrémente x | x après incrémentation |
| ++x | incrémente x | x avant incrémentation |
Utiliser ++x car égal a x+1 au niveau de ce que ca vaut







# Lecture 1

Almost every device run an os. And is a networked device. 
op : never stops and should never fail, it is trusted.

#### **Hardware Foundations of Computer Systems**  
The von Neumann Architecture : 
programs in memory, CPU has at least one register : instruction pointer(IP, I/O using special instructions. 
![[Pasted image 20240219101913.png]]

#### Protection and Memory Management Units
![[Pasted image 20240219101848.png]]

#### What is an OP

| operating | system |
| --- | --- |
| manage multiple users and tasks | interrelated parts with expected behavior |
 An operating system is  software layer that interfaces between diverse hardware resources and one or many applications running on the machine.
==The process : an abstraction easier to program than raw hard : ==
1. Referee : Manage protection, isolation, sharing of resources
2. Illusionist : Provides clean, easy abstractions on physical resources
3. Glue : provides a set of common services 


#### The OS as an illusionist
```C
#include
#include
#include <math.h>

int main(int argc, char *argv[]) 
{
	int *p = malloc(sizeof(int)); // Allocate 4 bytes of memory
    printf("(%d) p: %p\n", getpid(), p); // print pid and pointer value
    *p = 0; // setting the value to 0 
     while (1) { 
	    *p = *p + 1;
	     printf("(%d) p: %d\n", getpid(), *p); } }

```
 
# Lecture 2


Abstractions provide an interface to application programmers that separates policy—what the interface commits to accomplishing—from mechanism—how the interface is implemented. Ex:
Mechanism: A brake pedal Policy: I brake when I see a stop sign
Abstraction does :
hiding undesirable properties • adding new capabilities, and • organizing information


• Executable code: CPU instructions
• A process is an instance of an executable

### What is a process and what constitutes it ? 

• A unique identifier: Process ID : PID
• Memory image: • Code and data (static) • Stack and heap (dynamic) 
• CPU context: registers • Program counter, current operands, stack pointer 
• File descriptors: pointers to open files and descriptors


![[Pasted image 20240221084036.png]]

Stack : temp data, funct param, local var etc. From up to down
heap used for dynamic memory allocation. bottm to top. Stores struct
Data segment statically (known at compile time) allocates global variables and data structures
Read-only text segment contains code and constants. This is the program executable machine instructions

Not the same as a program, it is an instance of a program. 

| process | program |
| --- | --- |
| alive : open files, registers, mutable data | passive : code + data |

#### Sharing the ressources
time sharing : running one task at a time and quickly switch 
space sharing : each task gets a portion of the available space

## L02.2: The process state transition diagram
Process can be in one of : 
Running, Ready, Blocked. Zombie
![[Pasted image 20240221085522.png]]
Zombified if exit() while running

### OS mechanisms for process management

OS maintains process in process control blocks containing :
• PID • Process state / context 
• Pointers to parent process (cat /proc//status) 
• CPU context 
• Pointer to address space (cat /proc//maps) 
• IO status information 
• Pointer to a list of open files (file descriptors, cat /proc//fdinfo/*)


~~~C
fork();
exec();
exit();
wait();
~~~

fork() creates a new process (replica) with a copy of its own address space
exec() replaces the memory (address space), loads new program from the disk

~~~ C
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>


int main(int argc, char *argv[]) { 
	6 printf("Hello world, I'm PID: %d (%s)\n", (int)getpid(), argv[0]);
	int pid = fork(); 
	if (pid < 0) { 
		// fork failed 
	fprintf(stderr, "fork failed\n"); 
	exit(1);
	} else if (pid == 0) { 
		// child (new) process 
	printf("Hello, I am child (pid: %d)\n", (int)getpid()); 
	} else { 
		// Parent process execution path 
	printf("Hello, I am a parent of %d (pid: %d)\n",  
	pid, (int)getpid());
	} 
	return 0;
}
~~~

## L02.4: Case study How the shell execs programs

In basic OS: hardware initialisation then creation of init process which spawns a shell : bash, *Et cetera...

### Summary
![[Pasted image 20240221095219.png]]
