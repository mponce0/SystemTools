# Memory Model

For every process running in a computer, the OS assigns it a space in memory, which is called its **memory address*.
The memory model, attempts to describe the different parts of this memory space, its properties and assignations.
The different parts in this model are usually known as *segments*.


```
		[---------------------] 0x
		|	CODE	+------------+
		+---------------|  ROData    |
		|		+------------+
		|	  	+---------------+
		|  STATIC DATA	| .data		|
		|		| BSS segment	|
		|		+---------------+
		|---------------------|
		|	HEAP	      |
		|		      |
		|---------------------|-v
		|		      | v 
		|    	 unused       |
		|     	space 	      |
		|		      | ^
		|---------------------|-^
		|		      |
		|	STACK	      |
		+---------------------+ 2^32-1
```
