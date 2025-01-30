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

---

## Arrays & Pointers Dicothomy in C

Arrays and pointers are intimatedly related in C, but it must be clear that these are **not** the same!
They do share similarities but also important differences among them.

For starting an array is a collection of homogeneous (i.e. identical) elements' types.
One of the critical aspects of this, is that the compiler can optimize many operations
by taking advantage of this homogeneity.
Furthermore, arrays take full optmized advantages when they are lay down **contiguously** in memory.
Differently than in other programming languages, in C, arrays do not contain any addtional information, such as, number of elements or length of the array.
This already implies that when ever operating with arrays the actual size of it must be always included in functions' arguments.
Indexing in C begins at 0 and goes up to N-1, in an array with N elements.
The compiler will neither stop us from attempting to access an index of an array exceeding its intended size.
According to the language standards, the behaviour of exceeding array bounds is *undefined*, which means that, either:
  - program might appear to work
  - program might crash (segmentation fault)
  - program might do something apparently random.

Pointers on the other hand are just single variables, with the peculiarity that these are used to store *memory addresses*.

An *array name* in expression context decays into the array's *starting address* (address of
zero-th element).

Some confusion exists about C passing arrays by-reference as arguments to the functions.
We must be clear here, C **only passes by-value!!!**
The reason why this misinterpretation arises is because when passing an array to a function,
in the context of the function this *decays into the memory address of the first element of the array*,
hence this is passed by-value, ie. copied and within the function we have received a memory address where the
array begins.
So, when manipulation the "array" within the function we are indeed operating in the precise memory addresses where the array has been originally store.

Furthermore, any pointer can be used with the array access operator [ ].
The array access operator [ ] is in reality only a shorthand for *pointer arithmetics + dereference*.
Hence the following expressions are equivalent in C: `x[i] == *(x + i)`, being `x` an array and `i` an index.
In this case, the compiler resolves the name of an array to the starting address of the array and
adds to it.

But if pointers are just variables for storing memory addresses, then why pointers need to have a type?
In reality the pointer itself does not need it, however *pointer arithmetic* needs to know the size of object that
pointer points to so it knows by how much to increment to get to the next element.

So, to clarify arrays are not pointers, but they share many common aspects:
  - "Equivalence" of pointers and arrays
    Decay: An lvalue of type array-of-T which appears in an expression decays (with
three exceptions) into a pointer to its first element; the type of the resultant
pointer is pointer-to-T.
(The exceptions are when the array is the operand of a `sizeof` or `&` operator, or is a literal string initializer for a character array.)
  - Array and pointer declarations are interchangeable as function formal parameters
  - Arrays automatically allocate space, but can't be relocated or resized.
Pointers must be explicitly assigned to point to allocated space (perhaps using
malloc), but can be reassigned (i.e. pointed at different objects) at will, and have
many other uses besides serving as the base of blocks of memory.
  - Due to the so-called equivalence of arrays and pointers, arrays and pointers often
seem interchangeable, and in particular a pointer to a block of memory assigned by
`malloc` is frequently treated (and can be referenced using [] exactly) as if it were a
true array.


## Pointers ``Delicatesen''

Pointers are truly powerful tools, and as it usually happens with powerful tools
one must be careful as it can lead to unintended serious consequences when are missused.
With pointers we have direct access to memory and memory manipulation,
which allow us to directly operate in memory addresses hence affecting values
of related variables.

Some of the typical mistakes when working with pointers can be classified as:
  - *memory leaks*, this is refers to the case when memory that has been dynamically allocated typically by any of the `alloc`-family function calls, is not released.
    In some cases, this could be the result of "sloppy" programming, ie. just forgetting to `free` the memory that has been dynamically allocated.
    But in other cases, it could be that the actual memory address has been mishandle and we have lost access to it, so in this case an attempt to free the memory address wil be unsucessful.
  - *dangling pointers*,

Tools such a memory profiler, can help to identify this type of problems.
For instance one of the best memory profilers is **vagrind** -- https://valgrind.org/.

> *Exercise/Question:*
    What makes memory leaks dangerous?
    After all modern OS will release any memory address space for any program that has finished running.

---

## Important concept to understand:
   - C passes by-value
   - array name decay
   - de-reference
   - pointer arithmetics

---
