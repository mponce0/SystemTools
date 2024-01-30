# Introduction: "Software Tools and Systems Programming"

Welcome!

These are notes related to **Software Tools and Systems Programming** topics.
As such, they include a good number of tools or so-called *utilities* programs (i.e. "Software Tools") which allow us to perform different type of operations related to the system where we run them.
Ranging from monitoring resources, activities to perform specific actions or tasks.

They also include how to program and extract information directly from the operating system running on the computer, i.e. "Systems Programming".
In other words how to employ the resources (APIs) provided by the operating system to users, other programs, etc.

There will be two main elements playing critical and fundamental roles in these notes: the *Operating System* (OS) of the computer/device/system, and in particular the *Unix/Linux OS*.


## Operating System
An *operating system* (OS) is a software implementation that makes possible the utilization of the specific hardware where the OS runs.
It has critical responsibilites in making the hardware useful and usable by pother programs, users, etc.
In a very general way, it is an abstraction layer sitting directly on top of the hardware and all its complexities and peculiarities.
By doing this it makes the hardware accessible to other programs, applications, etc.
The OS is also a resource manager as it administrates resource allocations, operations management, etc. 
It oversees the propper and appropiate utilization and assignation of the system resources to programs, agents, applicatiopns, users, etc.

## Linux
As a very special type, and likely the most powerful OS implementation, we will focus on the Unix/Linux type.

In its very begginings, originated as the Unix OS, as the decades passed it evolved into its "modern" conception of the Liunx OS version.
Although the principles and philosophies remain qutie similar among these two distant variants.
Unix/Linux has a very rich history, and perhaps more interestingly initial conceived by the 1970s already as an OS that is:
  - multi-user, i.e. can support and handle mutiple iusers simultaneously
  - multi-process, i.e. can run and alternate among multiple programs/tasks/etc.
  - offers access control and managament of the system (hardware) resources.

One of the most interesting abstractions that the Linux OS does is to treat every single computer resource, including hardware components as **files**.
This has profound imnplications, in terms of the simplicity with which the OS can deal and manage devices as well as the powerful control and oversee the OS has.
However as we will discuss when talking about the FS, "files" won't just be the simple interpretation we may have about files but a much richer and more indepth consideration. 

* The Linux OS is a complex and vast software system, with multiple functionalities, systems and moving parts that intertwien their scopes and dynamnics.


### Open Source
Another core principle of the Linux philosphy, or design principles, is that Linux is a *free* and *open source* initiative.
I.e. that the source code, the actual programs that compose the OS are free to use and freely accessible to anyone and everyone.
One can just simply obtan the source code of the OS, look at it, modify it, improve, change it, adapt it to its own needs and preferences.

This is one of the core principles at which Linux supporters and adopters adhere to.
It has profound implications from the philosophical stand-point but also from pragmatical aspects as well.
As this implies that the OS source code can be inspect, reviewed by anypne willing to... interestingly enough this has become one of the strongest and most appealing features for many from the Linux OS (myself included!), of course in addition to its robustness, design principles, core secuity aspects, etc.



## Linux OS Components
The Linux OS is structured and architected in a modular fashion, with interchangeable and inter-connected components.
The main components in the Linux OS are:
  - its *kernel*
  - a *shell* interface
    

### Kernel
The kernel of the OS, is the core of the OS, where the OS implementation performs and deploys the basic functionalities, abstractions and simplifications of the hardware architecture where its has been installed.

The kernel of the OS, being this basal layer is really complex and complicated, having to serve multiple uses and manaqing multiple resources. 

An integrated view of this can be seen in the following resources:
 - https://makelinux.github.io/kernel/diagram/
 - https://makelinux.github.io/kernel/map/


### Shell
The shell is another component of the OS, interfacing between the users, programs, applications and the actual kernel functionalities.
Mosly focusing in the interactions with the FS, and further commands or tools, the shell serves as an extension of the OS's kernel.
The shell can be used to operate with files and the file system similar to what a "file exporer" graphical-user interface but with much more fine-control, precision and posible automation of the tasks that need to be peformed. 


## Variants
Not only Linux can be seen as a "variant" or branching from the original "Unix" distribution, but there are currently several more branches co-existing on modern computers.
For instance, MacOS was originated from a Linux version known as "BSD", Android --the famous mobile OS-- is basicslly a Linux mobile version.
Moreover there are many more versions of propper Linux OSes: Arch64, Debian, Ubuntu, SuSe, RedHat, etc.

See (https://en.wikipedia.org/wiki/History_of_Unix#/media/File:Unix_history-simple.svg)
[![Simplified History of the Unix/Linux OS](https://assets.digitalocean.com/articles/alligator/boo.svg](https://en.wikipedia.org/wiki/History_of_Unix#/media/File:Unix_history-simple.svg "Unix/Linux History")]

Considering all the possible variations and platforms were Linux can run, it is without any doubts the most popular OS accross many different platforms and architectures: used in personal computers, workstations, latpops, mobile devices, and in particular with absolute majority in data centers and super-computer centers.


## Distros
A typical way to differentiate Linux OS "falvours" is by composing different 'distributions' or "distros".
Linux OS is so modular and flexible, that one can create its very own personalized and customized "flavour" of Linux by combining different elements of the OS.
The main elements needed are:  the Linux kernel, shell utilities, a desktop environment, a package manager, etc.

