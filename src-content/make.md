# Make
`make` is a tool used for automating systematic tasks.
For instance, the compilation of code, processing of data or documents, etc.
Basically any repetitive taks which must be done in a systematic fashion could be done in a prett efficient manner by using `make`.

The way in which `make` works is by defining series of *rules*, *targets* and *dependencies*.
`make` is also capable of keeping track of timestamps and figure out when a dependency must be updated (i.e. re-compiled) based on the timestamps of the taret and dependencies associated to it.
For defining these relationships among rules-targets-dependencies, `make` uses s so-called *makefile*, which a plain-text file where these roles are defined.
makefiles can also include commands from the shell, variables and macro definitions.

## About Modularity
One aspect that is critical for taking full advantage of an automation tool like `make`,
is that the source code implementation must be **modular**.
So one immediate question, would then be: what is a "modular implementation" or "modularity"?

Certainly it is **NOT** a single file containing function definitions.
...
