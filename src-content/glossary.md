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
   - high-level, is a programming level that offers a lot of abstractions and pre-defined functionalities when writing programs. Examples of this are: Python, R, ...
   - low-level, refers to a programming level that is very close (low) to the hardware details is. Examples of this are: C, Fortran, assembly.

Another possible way to classify programming languages is based on how the *translation* from the source code into the machine code is done:
   - compiled,
      the program that has to be fully read by the compiler in order to be converted into binary code so that it can be executed in the computer.
      in general, compiled languages do not allow for dynamic typing, i.e. for changing on the fly the type of variable, and in part because of this are better performing than interpreted ones.
   - interpreted,
      the program is read line by line and execute by the interpreter. Because of this and other peculiarities, such as garbage collection, dynamic typing, etc.; is that interpreted programming languages are substantially slower in terms of run-time performance.
   

## Function
   Minimal unit of cohesive code implementation that can be re-used and its designed to implement a particular and well-defined task.


## Modularity
   A technique and strategy used to develop code that can be separated into different *units* (or modules) and in this way combined to generate more complicated and complex programs.
   Modular implementations offer several advantages: make the code more robust, allows for precise unit testing, portability, distribution, ease in version control, etc.
   In C, this achieve by implementing proper functions with arguments, avoid at all cost the use of global variables (which breaks modularity!) and the separation of:
   
   - function's declaration, in "`.h`" header files
   - function's implementation, in "`.c`" files


## Machine Code (binary code)
Computers can only understand an specific set of instructions, known as **binary code** -- mostly because these are written in binary format (i.e. using 0s and 1s), but sometimes also represented in octal (base-8) or hexadecimal (base-16).

## Source Code
Term used to refer to a program when the programming language used is *compiled* instead of interpreted.

## Pseudo-code
General way, usually language agnostic, of describing a prescription, recipe or algorithm.

## Script
used to specify the "source code", i.e. the implementation of the program used in *interpreted*-type programming languages.

## Monolithic Code
it refers to the source code of a program which it has been written without any modular implementation, i.e. without function definitions, proper code etiquette such indentation, etc.

## Spaghetti Code
usually a variation on _Monolithic Code_ where not only the code etiquette is not present but also indentation is completely arbitrary making it really hard to follow and read.

## Executable
Is the program, machine code, that is being generated from a source code and can be run in the computer.
It is composed by the translation of the source code into binary code.

## Compiler
Program used to read and process the *source code* and generate an executable that can be run in the computer.

   * standards
   specifying set of instructions and conventions at which a particular programming language would adhere.
   The main rational for defining different standards is to allow the incorporation of new techniques and still remain *back-compatible* with older versions of codes and languages.


## Interpreter
Program used by *interpreted* programming languages to read and process line by line the instructions provided.


## Compilation
Process of taking a source code and generate an executable or binary code, that can be run in the computer.
Differently from an interpreter the compiler will read the whole source code, analyze it, check for different type of error, even improve it in some cases, and make sure everything is proper place and form to generate a valid executable.
   * Stages/Phases:

      In general, there are 3 main compilation stages:

      - *pre-compilation*, where the compiler calls another program named *pre-compiler* to take care of pre-compile declarations, i.e. all instructions that being with "#", such as, macro definitions, include statements, etc.
      - *compilation*
      - *linking*

   * Compilation errors
      Produced by the compiler, these represent situations in which the compiler can not generate the corresponding binary code from a source code.
      Causes for this vary, but could include syntactical mistakes, improver instructions implementation, types mismatches, etc.

   * Warning Messages
      These observations and concerns raised by the compiler. Warning won't stop the compiler from generating an executable but in general are a symptom of something else that may not be working correctly or as we might expect to.
      In general the recommendation is to adjust the code until the compilation does not generate any warning messages or at least to understand why these are there.
      Recommended flags to use during compilation: ```-Wall``` and ```-Werror```.


## Bug
  ToBeCompleted

## Crash
  ToBeCompleted

## Debugger
Utility program used to trace and analyze the live execution of a program.
Used mostly to identify errors or problems with the implementation of a code.

## Library
Collection of external resources that can be used in a program by including their declarations in our code.
Eg. this is done using ```#include <...>``` in C, or ```import ...``` in Python.


## Run-time error
Error that occurs during the execution of a program.

## Memory Model
Theoretical abstraction and description of how variables and memory is laid down and organize.

## Variable
ToBeCompleted

## Boolean
Special type of variable that can only store two possible values (aka binary), usually represented as 0/1, or, True/False.

## Floating Point
  - Number
  - Representation

## Overflow
   ToBeCompleted

## Underflow
   ToBeCompleted

## Operating System (OS)
   ToBeCompleted
   - kernel

## Terminal
   Application (program) that gives access to the shell of the operating system (OS).

## Command Line --or-- Command Line Interface (CLI)
   Interface provided by the shell of the OS to interact with the file system (FS) and run applications and other programs.

## Arguments
   Information passed to functions or commands, they are used as input and modify or change the way in the command/function works, or as the target over which the command/function acts upon.

## Command Line Arguments (CLA)
   Additional parameters passed to commands run from the CLI.

## Flags
   Special type of CLA that can only take pre-defined values, usually preceded by '-' or '--'

## TTY
   Terminal Typewriter, refers to a connection to a machine done by a "real" (physical) terminal, e.g. when a user connects to the machine through its console.

## PTY
   Pseudo-Terminal, virtual connection done through a "virtual" (pseudo) terminal.

## PTS
   Pseudo Terminal Session, refers to the end-point a remote connection done through a "virtual" (pseudo) terminal from a different location.
   

## TUI
   Text User Interface, i.e. a user interface based on text or console.

## GUI
   Graphics User Interface, i.e. a user interface based on graphical interactions.


## EOF
   End of File, special indicator to denote the end of file/data/communication.


---

ver 0.1 -- Last modified: Jan. 2024
