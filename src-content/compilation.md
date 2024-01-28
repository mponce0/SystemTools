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
* Compilation:
    - `-E` preprocess only
    - `-S` compile only, not assmeble nor link
    - `-c` compile and assemble, not link
    - `-o` name output file
      
* Warnings:  `-Wall`, `-Werror`
* Debugging: `-g`
* Profiling/instrumentation: `-pg`
* Libraries: `-I`,`-L`,`-l`


* Example
  ```sh
    # Compilation of the source code "myProg.c"  using the C standar '99: --std=c99,
    # enabling warning and pushing them to errors: -Wall -Werror,
    # wiht optimization level 2: -O2,
    # linking with the math library: -lm,
    # generating an executable named "myExec": -o myExec
    gcc --std=c99 -Wall -Werror -O2 myProg.c  -lm  -o myExec
  ```
