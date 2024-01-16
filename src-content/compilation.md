# Compilation

## Compilation Stages

* Pre-compiler
   - deals with pre-processor instructions, syntax checking, etc.

* Compiler
   - conversion into binary/machine code
     
* Linker
   - link with external libraries


## Compilation Flags

* Optimization Flags: `-O0`, `-O1`, `-O2`, `-O3`
* Warnings:  `-Wall`, `-Werror`
* Debugging: `-g`
* Libraries: `-I`,`-L`,`-l`

* Example
  ```sh
    # Compilation of the source code "myProg.c"  using the C standar '99,
    # enabling warning and pushing them to errors,
    # wiht optimization level 2,
    # linking with the math library,
    # generating an executable named "myExec" 
    gcc --std=c99 -Wall -Werror -O2 myProg.c  -lm  -o myExec
  ```
