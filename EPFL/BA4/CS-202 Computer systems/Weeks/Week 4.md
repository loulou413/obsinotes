---
Week: 4
Themes: 
Lecture1: true
Lecture2: false
Exercises: false
---

  

## Notes

  

# Lecture 1
## L06.2 Pages tables
• A page table stores virtual-to-physical address translations
• Stores address translations for each virtual pages in the address space
• Allows MMU to know where in physical memory each virtual page resides
PTE : page table entry 
- Index i corresponds to virtual page number (VPN) i
- Contains the page frame (PFN)
## L06.3 TLB
• MMU walks PTE tree, starting at PTBR
Solution: a cache for virtual address to physical address mappings
Translating virtual address to physical address:
1. MMU first looks up TLB 
2. If TLB hit: physical address can be directly used 
3. Only if TLB miss: MMU “walks” page table

Key: the TLB is NOT in memory, but rather a special circuit


What is the typical content of the page table? • Page table entries (PTE) with permission bits
How big are the page tables? • Very big. Linear page table vs multi-level page table 
Does paging make the system slow? • Fortunately, TLB comes to the rescue 
What to do when running out of memory? • Swap pages from/to disk

## L06.4 How the OS leverages paging (two examples)

	 
# Lecture 2

## L07.1 IO stack 
The goal is persistence 

Given: Set of persistent blocks from a storage device 
Goal: Manage these blocks efficiently
![[Pasted image 20240313083101.png|300 ]] 
IO abstraction stack 

## L07.2 The file system abstraction
2 main components : files, directories
A file is named collection of related information that is recorded in secondary storage. It has 2 parts : 

| Data                                        | Metadata                                             |
| ------------------------------------------- | ---------------------------------------------------- |
| What a user or app puts in : array of bytes | info added and managed by the os : Size owner, infos |
Has 3 perspectives : 
1. inode (ID)
2. path (human readable)
3. file descriptor (process view) 


### Inode :  Low level unique ID.
Inodes are unique for a file system but not globally, recycled after deletion
Contains metadata : permissions, lenght, acces time 
#### Inode tables 
#### ![[Pasted image 20240313085608.png| 300]]
Storage space is split into inode table and data storage. 
File are statically allocated
Require inode number to  file content


#### User view : file name 
human readable name organized in hierarchies of directories : pathname


##### Path -> inode
A special file (directory) stores mapping between file names and inodes

##### Inode and directories 
Inode does not contain the file name
Each directory is a file there is only one bit in the inode that differences it
Multiple file names can map to the same inode 
-> inode has a reference count


#### Process view: file descriptor
The combination of file names and inode/device IDs are sufficient to implement persistent storage
• Drawback: constant lookups from file names to inode/device IDs are costly
• Idea: do expensive tree traversal once, store final inode/device number in a per-process table 
 1. Also keeps additional information such as file offset 
2. Per process table of open files 
3. Use linear numbers (fd 0, 1, 2 …); reuse when freed
![[Pasted image 20240313093129.png|500]]
### File system API 

Create a file : 
```c
 int fd = open("./out.txt", O_CREAT | O_RDWR | O_TRUNC, S_IRWXU) :  
 ```
	Returns a file descriptor (fd), that grants the capability to perform certain operations on the file
Close the file : int close(int fd)
## L07.4 file system implementation
• Given: a large set (N) of blocks
Need: data structures to encode file hierarchy and per file metadata 
	• Overhead (metadata vs file data size) should be low 
	• Internal fragmentation should be low 
	• Efficient access of file contents: external fragmentation, # metadata access 
	• Implement file system APIs
	
File allocation: Multi-level indexing

![[Pasted image 20240313095236.png|700]]

