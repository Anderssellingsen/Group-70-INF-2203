[[P2]]
[[P3]]

![[process's stack]]

This is how the stack of a process looks like 
```
	/*
	 * System V process start stack frame (after pushing EBP)
	 *
	 *	ebp+ 8	start of argv vector
	 *	ebp+ 4	argc passed by OS
	 *		(the typical return address is missing)
	 *	ebp+ 0	old EBP
	 */
```


C runtime is an assembly function that acts as a *_start* for each process. 

### How does it work? 

1) allocate a stack frame
2) Pushes argc and pointers to argvs into the stack. I386 architecture makes the stack grows downward when variables are pushed. 
3) calls main
4) deallocates the stacks by adding 8 bytes to the *esp*
5) calls *_exit*. Basically system call for exiting the process. 
