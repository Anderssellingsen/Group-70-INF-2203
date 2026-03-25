
--- 

The reason for separating the memory into two regions is because it is necessary to protect the entire OS from malicious processes. An example is the *eraser* program. It deletes a given area in the memory space.  

To perform any kernel level operation, e.g I/O operation, a process must do a [[system call]] so that kernel can consider and perform the operation. 

Computers at the beginning did not have memory protection. It means that processes have full access to any area of the memory.

![[protection levels]]
To protection levels are used to enforce memory protection. ***Only  level 0 and 3 are relevant for today's computer***
- Say that a process tries to access a kernel-level page. Given that process's pages only have user-level access, it will trigger an interrupt (*page fault*) and the kernel detects it, searches for the right *interrupt service routine* in the *interrupt descriptor table*

The levels are placed as flag in *global descriptor table entries* and/or *page table entries*   
- Why does protection level need to be in both ***global descriptor table and page table*** ?

[[GDT]]
[[interruption, IDT and ISR]]
[[page table hierarchy and paging]]
[[interruption, IDT and ISR]]