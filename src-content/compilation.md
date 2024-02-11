# Compilation

## Compilation Stages

* Pre-processor
   - deals with pre-processor instructions, syntax checking, etc.

* Compiler
   - conversion into assembly code 

* Assembly
   - conversion into binary/machine code (known as object file, `".o"`)

* Linker
   - link with external libraries


## Compilation Flags

* Optimization Flags:
    - `-O0`, `-O1`, `-O2`, `-O3`
    - `-Ofast`, `-march=<ARCH>`
  
* Compilation:
    - `-E` pre-process only; do not compile, assemble or link.
    - `-S` compile only; do not assemble or link.
    - `-c` compile and assemble, but do not link.
    - `-o <execName>` name output file
      
* Warnings:  `-Wall`, `-Werror`
* Debugging: `-g`
* Profiling/instrumentation: `-pg`
* Libraries: `-I`,`-L`,`-l`

* Misc.:
    - `--std=<std_ver>`  
    - `-v`  display built-in specs.
    - `--version`  display compiler version


* Example
  ```sh
    # Compilation of the source code "myProg.c"  using the C standard '99: --std=c99,
    # enabling warning and pushing them to errors: -Wall -Werror,
    # with optimization level 2: -O2,
    # linking with the math library: -lm,
    # generating an executable named "myExec": -o myExec
    gcc --std=c99 -Wall -Werror -O2 myProg.c  -lm  -o myExec
  ```
