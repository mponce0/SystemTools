# The File System

In a very basic way the **file system** can be considered as the components of the OS in charge of *managing and administrating files*.

The file system defines how data is stored, accessed, and organized on storage devices.
Different file systems have varying characteristics and are often specific to certain operating systems or devices.

By now, we understand that a "file" is just not the typical construct we have about the data stored on it but also all the information related to it, such as its metadata, and more fundamental aspects like inodes, blocks, etc.

In particular in Unix and Linux type OSes, a file plays a critical role: **any single resource in the comptuer system is described as a file**.
This unique perspective makes this abstraction at the level of the OS, one of the most powerful one but also one of the most versatile and usefull one.

In order for the OS to manage files, it employs two critical elements:

## Blocks
   - abstractions of data on the filesystem
   - have a fixed size, detemrined at the time the filesystem is created
   - the *block size* determines how many butes are allocated to each block
   - they represent the *minimal unit* of information on the specific filesystem
   - In general, block sizes are 1 KB, 2 KB, or 4 KB for 32-bit systems; and 8 KB is also available on 64-bit systems.

## Inodes (index node)
  - data strcture used to map blocks to physical locations in the hardware storage device (e.g. a disk or hardrive)
  - every single file gets assigned an inode
  - in some way one could think about them as being analogous to pointers
  - when a filesystems runs out of inodes, no new files can be created until existing files are deleted
  - Useful commands to investigate inodes: `ls -i`, `df -i`

---

### Diagram displaying the different elements from the OS, FS and hardware that makes possible the access (storage and retrieval) of information in not volatile devices

```
   Operating System           ||      STORAGE DEVICE
                  (( F i l e    S y s t e m ))
      - inodes
         / | \            [firmware]
        |  |  |           [drivers/controllers]
        v..v..v
      - blocks   ---  ---  ---  --- ---> sectors

```
---

We should mention the distintion among the "File System" as a component of the OS, and the filesystem actually related to specific storage devices.
This distintion plays a critical role, when in reality you speak to different professional from different fields.
For a system administrator in a typical data center or supercomputer center, it is qwuite likely that the FS is referring to the actual hardware and supporting drivers or firmware in charge of making it functional and accessible to the OS.

Moreover is possible that a computer system and its corresponding OS, operate on multiple and different types of file systems simulatenously.

```
   [system ]
   [ OS/FS ]
      |  \  \
      |   \  +~~~~(NAT-FS)
      |    +~~~~~~(alien-FS/external-drive)  
(OS-native) 
(filesystem)

```

Importantly, the "view" that the OS And FS have of the files and their associated data is quite different from the one that users or even programs and applications perceive.
From an user perspective, the files, directories, etc. appear as a well organized, hierarchically structured formation -- see the "Typical Linux FS Directory Structure".
However, this is another of the "nice" abstractions and simplified view that the OS in combination with the FS present to users and applications.

A more "realistic view" is the intertwiened relationships mantained among inodes, blocks and even sectors; with its corresponding mapping and distributed pointes and links.


### Different type of filesystems:
When talking specifically about the filesystem in terms of the characteristics of how the data and metadata is presented and layout in relation to the hardware, it should be noticed that there are many different types.
The following is an incomplete, but still interesting and representative, list of the different type of filesystems: 
   - FAT:  One of the oldest and simplest file systems. It was initially developed for MS-DOS and is still used in many removable storage devices. The two major versions of this system are FAT16 and FAT32. FAT uses a file allocation table to keep track of file locations on the disk. Used in Windows before NTFS was introduced.
   - exFAT: The extended File Allocation Table (exFAT) builds on FAT32 and offers a lightweight system without all the overhead of NTFS.
   - NTFS: The New Technology File System (NTFS) is the file system that modern Windows versions use by default.
   - HFS+: The Hierarchical File System (HFS+) was the file system older Macs used by default.
   - APFS: The proprietary Apple file system developed as a replacement for HFS+, with a focus on flash drives, SSDs, and encryption.
   - ext2, ext3, & ext4: The extended file system (ext) was the first file system created specifically for the Linux kernel.

   - GPFS: a General Parallel File System, proprietary FS developed by IBM for HPC or cluster-type systems.
   - NAS: Network Attached Storage, involves a server connected to a network providing access to storage resources.


## File Interfaces in C/Unix

There are two main mechanisms for managing open files:
   * File descriptors:
        - these are low-level, managed by OS
        - Each open file is identified by a small integer
        - For instance, `STDIN` is 0, `STDOUT` is 1

   * File pointers:
      - also known as streams or file handles,
      - these are aimed/used for "regular" files
      - A C language construct for easier working with file descriptors
      - You use a pointer to a file structure (`FILE *`) as handle to a file.
      - The file struct contains a file descriptor and a buffer.

### Standard File Descriptors
The operating system (OS) maintains for each process a table with *open file descriptors*, the so-called **file descriptor table**

For each process in the system, the OS automatically opens the three standard file descriptors:

|                 |   Name   |   File Descriptor   |   Default   |
|-----------------|----------|---------------------|-------------|
| Standard Input  | `stdin`  |   0                 |   keyboard  |
| Standard Output | `stdout` |   1                 |   screen    |
| Standard Error  | `stderr` |   2                 |   screen    |


## File System Tables
The OS system will mantain *in-memory structures* to manage and track open files.
It does this by using a combination of of tables and cross-referencing processes, file descriptors and files (using inodes).

Each time a file is opened, a new entry is added to these structures.
The process involves finding the corresponding inode for the given file, check permissions from the metadata and initialize/poition the *cursor* at the beggining of the file.

The in-memory structures mantained by the OS are:
   * **Process Control Block**
     
        a table containinf the *File Descriptor Table* for each process where eery single file opened by the process has an entry

      |  FD |  filename  |
      |-----|------------|
      |  0  |  stdin     |
      |  1  |  stdout    |
      |  2  |  stderr    |
      |  3  |  data.txt  |
      |  4  |  data2.dat |
      | ... |  ...       |
     
* **System-Wide Open File Table**

  The list of all files opened in the system, with its current cursor positioning

     | System-Wide Open Table |
     |------------------------|
     | STDIN                  |
     | STDOUT                 |
     | STDERR                 |
     | data.txt, offset, ...  |
     | data2.txt, offset, ... |
     | ... , ...              |
  
  
* **Vnode Table**
  
  The list of all inodes associted to the open files.
  
     | Vnode Table   |
     |---------------|
     | inode X, ...  |
     | inode Y, ...  |
     | ...           |


A generic and typical "relational" representation would be,

```
[[ Process i ]]
|  Process Control Table  |
|| File Descriptor Table ||
||   0   stdin           ||
||   1   stdout          ||
||   2   stderr          ||            |  System-Wide Open File Table  |        |  Vnode Table     |
||   3   data.txt        ||.......     ||   STDIN                     ||   :--->||  inode X, ...  ||
||   4   data2.dat       ||      :     ||   STDOUT                    ||   :    ||  inode Y, ...  ||
||   5   sample.txt      ||      :     ||   STDERR                    ||   :    ||  inode Z, ...  ||
|-------------------------|      ----->||   data.txt , offset, ...    ||...:    ||   . . .        ||
                                       ||   data2.dat , offset, ...   ||        ||   . . .        ||
[[ Process j ]]                        ||   sample.txt , offset, ...  ||        ||   . . .        ||
|  Process Control Table  |      :---->||   data.bin , offset, ...    ||        |------------------|
|| File Descriptor Table ||      :     ||   data2.dat , offset, ...   ||
||   0   stdin           ||      :     ||   . . .                     ||
||   1   stdout          ||      :     ||   . . .                     ||
||   2   stderr          ||      :     ||   . . .                     ||
||   3   data.bin        ||......:     |-------------------------------|
||   4   data2.dat       ||
|-------------------------|

```


## File Input/Ouput Operations (IOPs)
Now that we have a more "low level" view of what a file is for the OS and FS, we should clarify that accessing --i.e. reading and writing data from/to files-- is just not qhen single opeartion.
Usually this process involves multiple operations, actions and manipulations from the OS.

### Basic I/O opearations
   - Finding a file (`ls`)
     - Check if that file exists, read metadata (file size, date stamp etc.)
   - Opening a file:
      Check if that file exists, see if opening the file is allowed, possibly create it, find the block that has the (first part of) the file system.
   - Reading a file
       Position to the right spot, read a block, take out right part
   - Writing to a file:
      Check where there is space, position to that spot, write the block. Repeated if the data read/written spans multiple blocks.
   - Move the file pointer (*seek*):
      File system must check were on disk the data is.
   - Close the file.


### Basic File I/O Functions (`stdio.h`)

```C
// Open
FILE *fopen(const char *path, const char *mode);

// Input:
int fscanf(FILE *stream, const char *format,...);
char *fgets(char *s, int size, FILE *stream);
char fgetc(FILE *stream);

// Output:
int fprintf(FILE *stream, const char *format,...);
int fputs(const char *str, FILE *stream);

// Position cursor:
int fseek(FILE *stream, long int offset, int whence);
void rewind(FILE *stream);

// Close
int fclose(FILE *stream);
```



### A tale of Hierarchies
IOPS are the most expensive operations of any program, hence one must deal with them with caution and in most the cases attempting to minimize them.
The reason why that's the case is because the access to information storage in storage devices ia the slowest part in modern computers, even if one considers solid-state devices (SDDs) the typical time frame is going to be orders of magnitudes larger than the number of operations perform by the micro-processor.

```
  speed    #cyles                                            capacity
  fastest   o(1)                    RX                        small       |
    ^       o(10)                 cache                         |         | on-chip
    |       o(100)              main memory                     |        || in-board
    |       o(100)         Solid State Devices (SSD)            |       ||| 
    |       o(1000)    Traditional Spining Devices (HDD)        |       ||| outboard
    |       o(10000)         Optical disks (CD)                 V      ||||
    |       o(100000)           Magnetic Tape                 large    |||| offline
  slowest   o(1000000)       Network Communication                    ||||| offsite
```


## Typical Linux FS Directory Structre
```sh
/
├── bin -> usr/bin
├── boot
├── dev
├── etc
├── home
├── lib -> usr/lib
├── lib64 -> usr/lib
├── mnt
├── opt
├── proc
├── root
├── run
├── sbin -> usr/bin
├── srv
├── sys
├── tmp
├── usr
└── var
```

The listing above displays the typical directory structure in a Linux-type OS.
As such these directory entries have some standariozed meaning and purpose, e.g.
   - `/`: this is known as the "root" directory, o.e. the 'top'-level in the directory struture
   - `/bin`: stands for "binary", and it used to place basic programs and utilities, such as `ls` or `cp`, etc.
   - `/boot`: information about the booting of the system is placed here
   - `/dev`: file representation for devices are located in this directory
   - `/etc`: system-wide configuration files and databases are located here
   - `/home`: location for placing users' home directories
     - `/home/marcelo`
   - `/lib`: contains shared libraries needed by programs in `/bin` or kernell modules
   - `/mnt`: place-holder directory used to "mount" other FS, i.e. a temporary mounting point
   - `/opt`: contains locally installed software
   - `/proc`: a virtual file system ("procfs") containing information about all the currently running processes 
   - `/root`: home directory of the system administrator: super-user (also known as "root", not to be confused with the root of the directory's tree)
   - `/sbin`: super-user binarires (sbin)
   - `/srv`: server data, data for services provided by the system
   - `/sys`: another virtual FS ("sysfs") containing information about the hardware and OS
   - `/tmp`: temporary directory
   - `/usr`: "user" directory aimed to hold executables, libraries, and shared resources that are not system critical
     - `/usr/local`
     - `/usr/share`
   - `/var`: a location to place varaible content, i.e. that might change frequently
     - `/var/log`: system logs
     

## References
   - Interesting reading:
       "Anatomy of the Linux file system", https://developer.ibm.com/tutorials/l-linux-filesystem/
