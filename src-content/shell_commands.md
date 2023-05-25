# Shell
A shell is sometimes referred as a *meta-program* capable of running
other programs.
More importantly it sits directly as an interface between the user, APIs,
etc. and the *kernell* of the OS.

# Commands
```sh
# files/directories
pwd
cd  # cd - (go to previous directory)  |  cd ~ (go to home-dir)
mkdir
rmdir

ls
cp
mv
rm

# permissions
chmod
chown

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
..    # upper directory
/     # root directory
~     # home directory
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
   * 
