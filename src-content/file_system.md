# The File System

In a very basic way the **file system** can be considered as the components of the OS in charge of *managing and administrating files*.
By now, we understand that a "file" is just not the typical construct we have about the data stored on it but also all the information related to it, such as its metadata, and more fundamental aspects like inodes, blocks, etc.

In particular in Unix and Linux type OSes, a file plays a critical role: any single resource in the comptuer system is described as a file.
This unique perspective makes this abstractions in the OS, one of the most powerful ones but also one of the most versatile and usefull ones.

In order for the OS mangae files it employs two critical elements:

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


## File Input/Ouput Operations (IOPs)


## Typical Linux File System
```sh

```
