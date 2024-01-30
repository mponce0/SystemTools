# The File System

In a very basic way the **file system** can be considered as the components of the OS in charge of *managing and administrating files*.

The file system defines how data is stored, accessed, and organized on storage devices.
Different file systems have varying characteristics and are often specific to certain operating systems or devices.

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
  - Useful commands to investigate inodes: `ls -i`, `df -i`

---

We should mention the distintion among the "File System" as a component of the OS, and the filesystem actually related to specific storage devices.
This distintion plays a critical role, when in reality you speak to different professional from different fields.
For a system administrator in a typical data center or supercomputer center, it is qwuite likely that the FS is referring to the actual hardware and supporting drivers or firmware in charge of making it functional and accessible to the OS.

Moreover is possible that a computer system and its corresponding OS, operate on multiple and different types of file systems simulatenously.

Importantly, the "view" that the OS And FS have of the files and their associated data is quite different from the one that users or even programs and applications perceive.
From an user perspective, the files, directories, etc. appear as a well organzied, hierarchically structured formation -- see the "Typical Linux FS Directory Structure".
However, this another of the "nice" abstractions the OS in combination with the FS present to users and applications.

A more "realistic view" is the intertwiened relationships mantained among inodes, blocks and even sectors; with its corresponding mapping and distributed pointes and links.

## File System Tables


### Different type of FS:
   - FAT:  One of the oldest and simplest file systems. It was initially developed for MS-DOS and is still used in many removable storage devices. The two major versions of this system are FAT16 and FAT32. FAT uses a file allocation table to keep track of file locations on the disk. Used in Windows before NTFS was introduced.
   - exFAT: The extended File Allocation Table (exFAT) builds on FAT32 and offers a lightweight system without all the overhead of NTFS.
   - NTFS: The New Technology File System (NTFS) is the file system that modern Windows versions use by default.
   - HFS+: The Hierarchical File System (HFS+) was the file system older Macs used by default.
   - APFS: The proprietary Apple file system developed as a replacement for HFS+, with a focus on flash drives, SSDs, and encryption.
   - ext2, ext3, & ext4: The extended file system (ext) was the first file system created specifically for the Linux kernel.

   - GPFS: a General Parallel File System, proprietary FS developed by IBM for HPC or cluster-type systems.
   - NAS: Network Attached Storage, involves a server connected to a network providing access to storage resources.


## File Input/Ouput Operations (IOPs)


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
     
