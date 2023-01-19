# Glossary

## Algorithm
is a generic prescription or recipe to tackle a particular problem, it does not depend on the details of the implementation; i.e. you can think of it as the general guidelines to solve any problem independent of any particular programming language

## Program
precise series and sequence of instructions, specifying the actions to be followed by a computer in an specific *programming language*.

## Programming Language
Set of instructions, standards, rules and specifications follow to be translated into *machine code* to be executed by the computer.
Examples: Python, C, C++, Java, Fortran, R, C#, etc.

There are several ways in which programming languages are grouped or classified.

For instance, they can be grouped by how "close" to the actual hardware and 
   - high-level, is a programming level that offers a lot of abstractions and pre-defined functionalities when writting programs. Examples of this are: Python, R, ...
   - low-level, refers to a programming level that is very close (low) to the hardware details is. Examples of this are: C, Fortran, assembly.

Another possible way to classify programming languages is based on how the *translation* from the source code into the machine code is done:
   - compiled,
      the program that has to be fully read by the compiler in order to be converted into binary code so that it can be executed in the computer.
      in general, compiled langauages do not allwo for dynamic typing, i.e. for changing on the fly the type of variable, and in part because of this are better performing than interpreted ones.
   - interpreted,
      the program is read line by line and execute by the interpreter. Because of this and other pecularities, such as garbage collection, dynamic typing, etc.; is that interpreted programming languages are substantially slower in terms of run-time performance.
   

## Function

## Modularity


## Machine Code (binary code)
Computers can only understand an specific set of instructions, known as **binary code** -- mostly because these are written in binary format (i.e. using 0s and 1s), but sometimes also represented in octal (base-8) or hexadecimal (base-16).

## Source Code
Term used to refer to a program when the programming language used is *compiled* instead of interpreted.

## Pseudo-code
General way, usually language agnostic, of describing a prescription, recipe or algorithm.

## Script
used to specify the "source code", i.e. the implementation of the prrogram used in *interpreted*-type programming languages.

## Monolithic Code
it referers to the source code of a program which it has been written without any modular implementation, i.e. wihtout function definitions, proper code etiquete such indentation, etc.

## Spaghetti Code
usually a variation on _Monolithic Code_ where not only the code etiquette is not present nbut also indentation is completelly aribitrary making it really hard to follow and read.

## Executable
Is the program, machine code, that is being generated from a source code and can be run in the computer.
It is composed by the translation of the source code into binary code.

## Compiler
Program used to read and process the *source code* and generate an execurtable that can be run in the computer.

   * standards
   specifying set of instructions and conventions at which a particular programming language would adhere.
   The main rational for defining different standards is to allow the incorporation of new techniques and still remain *back-compatible* with older versions of codes and languages.


## Interpreter
Program used by *interpreted* programming lanuages to read and process line by line the instructions provided.


## Compilation
Process of taking a source code and generate an executable or binary code, that can be run in the computer.
Differently from an interpreter the compiler will read the whole source code, analyze it, check for different type of error, even improve it in some cases, and make sure evrything is proper place and form to generate a valid executable.
   * Stages/Phases:

      In general, there are 3 main compilation stages:

      - *pre-compilation*, where the compiler calls another program named *pre-compiler* to take care of pre-compile declarations, i.e. all instructions that being with "#", suhc as, macro definitions, include statements, etc.
      - *compilation*
      - *linking*

   * Compilation errors
      Produced by the compiler, these represent situations in which the compiler can not generate the corresponding binary code from a source code.
      Causes for this vary, but could include syntaxtical mistakes, improver instructions implementation, types missmatches, etc.

   * Warning Messages
      These observations and concerns raised by the compiler. Warning won't stop the compiler from generating an executable but in general are a sympton of soemthing else that may not be working correctly or as we might expect to.
      In general the recommendation is to adjust the code until the compilation does not generate any warning messages or at least to understand why these are there.
      Recommended flags to use during compilation: ```-Wall``` and ```-Werror```.


## Debugger
Utility program used to trace and analyuze the live execution of a program.
Used mostly to identify errors or problems with the implementation of a code.

## Library
Collectiion of external resources that can be used in a program by including their decalations in our code.
Eg. this is done using ```#include <...>``` in C, or ```import ...``` in Python.


## Run-time error
Error that occurs during the execution of a program.

## Memory Model
Theoretical abstraction and description of how variables and memory is laid down and organize.

## Variable

## Boolean
Special type of variable that can only store two possible values (aka binary), usually represented as 0/1, or, True/False.

## Floating Point
  - Number
  - Representation

## Overflow

## Underflow

## Operating System (OS)

## Flags

## Arguments

## Terminal

## Command Line


---

ver 0.1 -- Last modified: Jan. 2023
