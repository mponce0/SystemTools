# Shell
A shell is sometimes referred as a *meta-program* capable of running
other programs.
More importantly it sits directly as an interface between the user, APIs,
etc. and the *kernel* of the OS.

The *shell* can be considered a special  type of program that allows the user to interact with certain aspects of the OS.
In particular it allows us to manipulate and handle files in a very powerful and precise manner.
It also gives us access to specific features of the OS and the file system.
There are different types of shells, some are older or more basic, some others are newer and modern.
For instance, these are some of the most traditional ones: `sh`, `csh`, `tcsh`, `bash`;
and  these are more modern ones: `zsh`, `fish`.

There are common elements to any type of shell:
    the *prompt* is and indication that the shell is ready to receive instructions from the user;
    the *cursor*, usually a square or rectangle shaped character, many times blinking, awaiting for the user's input
-- the combination of these elements are known as the command line interface.
The most typical way to interact with the shell is via its **command line interface (CLI)**.
The CLI allows users to input commands to perform very specific actions.
The way in which these commands work is by performing very well-defined, usually
simple and narrow tasks.
But one of the main advantages of the shell is that it allows us to combine
multiple of these commands to perform more complicated or elaborated tasks.
The typical way to invoke these commands is using the command's name followed
by arguments to this program, usually known as command line arguments (CLA)
which are separated by "spaces".

### Generic Way to Execute Commands in the shell
```sh
   CMD [arg1] [arg2] [...] arg_i arg_ii ...
```
where `[]` represents *optional* arguments; i.e. arguments which can or can not be present at the moment of executing the command.

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
cat    # print file contents
more    # scroll through file
less    # scroll through file

head    # print first lines of a file
tail    # print last lines of a file

# search within files
grep    # search for text within a file

# compare differences
cmp    # compare binary files
diff    # compare text files
vimdiff    # compare text files with vi-interface

##

# binary files
hexdump
od

file    # determine type of file

which    # locate programs
whereis    # find files associated to commands
locate    #
find    # search for files

##

wc    # count characters, lines, words
awk    # 
sed    #

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

## Redirection and Piping
One of the most powerful features of the shell is its ability to very easily combine the actions and results from multiple commands.
It does this in two main ways:
    - by *redirecting* the expected output from a command into a file, and then this file used as an intermediary for the input of a second command; or
    - by directly shipping the output from the command into a second command, or commonly known as *piping*

A couple of comments/observations should be made here:
    1) you may recall and have noticed that most if not all of the shell commands appear top be very "simple" and do one thing mostly, this is not random but by design, in this way commands should focus in doing a very precise, concrete, well-define action (do it right!) and then these "simple" commands can be combined to lead to a more complex action;
    2) again, everything is a file in Linux and files are manipulated so easily and powerfully at the level of the shell, that it couldn't be clearer the critical role they have in the OS abstraction;
    3) having said that one must be careful when "hammering" file IOPs, shall we recall the IOPs hierarchy and penalties we incur by hitting the FS to frequently -- for this very same reason, communicating directly between commands is much efficient and preferable whenever possible, i.e. piping!

|  Redirection/Pipe |    Action    |    Example    |
|-----------------|-----------------------------------------|-------------------------|
| `cmd > file`    |    redirect standard output to a file   |    `ls -l > listing`    |
| `cmd >> file`   |    append standard output to a file     |    `ls -l >> listing`   |
| `cmd < file`    |    use file as input to cmd             |                         |
| `cmd1 \| cmd2`  |    pipe (pass) standard output from cmd1 to cmd2    |    `ls -l | wc -l`    |


### Special Redirections
As discussed before, standard output (stdout) and standard error (stderr) are de-facto
file descriptors created and orchestrated by the OS for any running process.
These can be also handle programmatically or from the shell.

 * For redirectiong standard error to standard output, use:
    `2>&1`

 * For redirecting both standard output and standard error to a file, use:
    `&>`

 * Example:
    `cmd &> filename`  --or-- `cmd > filename 2>&1`



## Refs.
   * https://www.kernel.org/doc/man-pages/
   * https://man7.org/tlpi/index.html
   * http://linuxcommand.org
