# Memory Model

For every process running in a computer, the OS assigns it a space in memory, which is called its **memory address*.
The memory model, attempts to describe the different parts of this memory space, its properties and assignations.
The different parts in this model are usually known as *segments*.


## The Address Space
   * **Code/Text**:
       binary code loaded into this region to get executed
     
       - **ROData**:
		read-only data region for string literals; depending on the platform it can be located in the static data segment instead.
     
   * **Static Data**:
     	space for *evil* global variables and variables declared as `static`
	Within the static data segment there are two additional sections:

        - **.data**:
		global or static variables with predefined values that can be modified
        - **BSS segment**:
		global/static variables without predefined values

   * **Dynamic Data (Heap)**:
    	space for dynamically allocated data structures (e.g. using `malloc, calloc`)

   * **Stack**:
        space for variables created in function calls, a function's parameters and function's local variables
     

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
