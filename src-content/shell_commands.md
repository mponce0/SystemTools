# Shell
A shell is sometimes referred as a *meta-program* capable of running
other programs.
More importantly it sits directly as an interface between the user, APIs,
etc. and the *kernell* of the OS.

# Commands
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

## Special Filenames
```sh
.     # current directory
..    # upper (parent) directory
/     # root directory
~     # user's home directory
```

## Special files
```sh
/dev/shm    # RAMdisk
/dev/null

/proc/cpuinfo
```

## File Descriptors
```sh
STDIN    0
STDOUT   1
STDERR   2
```

# Refs.
   * https://www.kernel.org/doc/man-pages/
   * https://man7.org/tlpi/index.html
   * http://linuxcommand.org
