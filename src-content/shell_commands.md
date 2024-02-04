# Shell
A shell is sometimes referred as a *meta-program* capable of running
other programs.
More importantly it sits directly as an interface between the user, APIs,
etc. and the *kernell* of the OS.

The *shell* can be considered a special  type of program that allows the user to interact with certain aspects of the OS.
In particular it allows us to manipulate and handle files in a very powerful and precise manner.
It also gives us access to specific features of the OS and the file system.
There are different types of shells, some are older or more basic, some others are newer and modern.
For instance, these are some of the most traditional ones: `sh`, `csh`, `tcsh`, `bash`;
and  these are more modern ones: `zsh`, `fish`.

There are common elements to any type of shell:
    the *prompt* is and indication that the shell is ready to receive instructions from the user;
    the *cursor*, usually a square or rectangle shapped character, many times blinking, awaiting for the user's input
-- the combination of these elements are known as the command line interface.
The most typical way to interact with the shell is via its **command line interface (CLI)**.
The CLI allows users to input commands to perform very specific actions.
The way in which these commands work is by peforming very well-defined, usually
simple and narrow tasks.
But one of the main advantages of the shell is that it allows us to combine
multiple of these commands to perform more complicated or ellaborated tasks.
The typical way to invoque these commands is using the command's name followed
by arguments to this program, usually known as command line arguments (CLA)
which are separated by "spaces".

### Generic Way to Execute Commands in the shell
```sh
   CMD [arg1] [arg2] [...] arg_i arg_ii ...
```
where `[]` represents *optional* arguments; i.e. argumwents which can or can not be present at the moment of executing the command.

For instance,
```sh
# the ls command, lists the content of the current directory
# in this case is used without any CLA
ls

# we can use a specific CLA: -l, known as a "flag" to instruct ls to provide more details
ls -l

# or we can even modify the directory where ls is going to list its content, in this case in the "root" directory of the system
ls /

# we can also combine multiple CLAs
ls -l /
```

Moreover, because the shell runs an interpreter to process these commands, it is possible to combine these commands in a file and process them in *batch mode*.
This is also known as *shell scripting*.


## Shell Commands

```sh
# files/directories
pwd  # print current working directory
cd   # change directory
  # special uses:
  #  cd -   =>  goes to previous directory
  #  cd ~   =>  goes to home-dir
  #  cd ..  =>  goes to upper (parent) directory
mkdir  # create a directory
rmdir  # remove a directory

ls  # list files
cp  # copy files
mv  # move or rename files
rm  # delete files

# permissions
chmod  # change access modes
chown  # change ownership

#

echo

# display text files
cat
more
less

head
tail

# compare differences
cmp
diff
vimdiff

##

# binary files
hexdump
od

##

wc
awk

##

watch

##

man

## code editor
vi
```

See [table of shell commands](shell_commands_table.md) and [list of tools/utilities](tools.md) for further details.


### Special Filenames
```sh
.     # current directory
..    # upper (parent) directory
/     # root directory
~     # user's home directory
```

### Special files
```sh
/dev/shm    # RAMdisk
/dev/null

/proc/cpuinfo
```

### File Descriptors
```sh
STDIN    0
STDOUT   1
STDERR   2
```

## Refs.
   * https://www.kernel.org/doc/man-pages/
   * https://man7.org/tlpi/index.html
   * http://linuxcommand.org
