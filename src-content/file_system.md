# The File System

In a very basic way the **file system** can be considered as the components of the OS in charge of *managing files*.
By now, we understand that "files" is just not the typical construct we have about the data stored in these files but also all the information related to them, such as its metadata, and more fundamental aspects like inodes, blocks, etc.

## Blocks
   - abstractions of data on the filesystem
   - have a fixed size, detemrined at the time the filesystem is created
   - the *block size* determines how many butes are allocated to each block
   - they represent the *minimal unit* of information on the specific filesystem

## Inodes
  - data strcture used to map blocks to physical locations in the hardware storage device (e.g. a disk or hardrive)
  - every single file gets assigned an inode
  - analogous to pointers
  - when a filesystems runs out of inodes, no new files can be created until existing files are deleted


## File Input/Ouput Operations (IOPs)


## Typical Linux File System
```sh

```
