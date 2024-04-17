---
Week: 5
Themes: 
Lecture1: false
Lecture2: false
Exercises: false
---

  

 Notes

  

# Lecture 1
## Part 2: Limited direct execution
Direct : cpu execute directly from the process's code
Limited : must be non privileged actions and may be interrupted 


How can it be interrupted ?
interrupt : asynchronous signal : sent to CPU, something happened outside of the process, ex : timer interrupt, I/O interrupt
trap : Synchronous signal: raised by the CPU because the process needs OS assistance, ex : system calls


## Part 3: Weird system calls


## Part 5 : segmentation vs paging

### Segmentation 
● Process (virtual) address space is organized into variable-size chunks (segments)
● Each segment is mapped to a contiguous set of physical addresses 
● MMU needs: base and bound per segment
### Paging 
● Process (virtual) address space is organized into fixed-size chunks (pages) 
● Each page is mapped to a contiguous set (frame) of physical addresses 
● MMU needs: page-to-frame map
  

# Lecture 2
