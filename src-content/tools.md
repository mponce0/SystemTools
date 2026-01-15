| Tool   | Description       |  Example |
|--------|-------------------|----------|
| `top`/`htop`/`atop`/`btop` | process and resources manager   |
| `ps`/`pstree` | process manager | `ps aux` |
| `uname`   |   system information  |   `uname -a`  |
| `netstat` | network analyzer  |
| `lsof`  | list file descriptors of open files |
| `tmux` / `screen` | terminal multiplexer |
| `tree` | display file tree structure | `tree --inodes` |
| `stat` | display file status | 
| `hexdump` | display file contents in hexadecimal, decimal, octal, or ascii |
| `od`  | dump files in octal and other formats    |
| `objdump` | display information from object files |
| `xxd` | creates a hex dump (or reverse) of a given file or standard input |
| `strace` | trace system calls and signals |
| `nm` | list symbols from object files |
| `size` | list section sizes and total size of binary files |
| `ldd` | prints the required shared objects (shared libraries)  | `ldd `_executable_  |
| `gdb`/`lldb`  | debugger |    See https://lldb.llvm.org/use/map.html for GDB/LLDB command mapping |
| `gprof` | profiler |  
| `valgrind` | memory profiler |  https://valgrind.org  |
| `ssh` | secure connection to remote servers | 
| `scp` | secure copy of files between remote machines |
| `rsync` | remote synchronization of files between remote machines |
| `vnc` | virtual network computing, connection to remotes servers  | `vncserver` |
| `curl`/`wget` |   transfer files from a given URL (internet)  |
||
| `grep`/`egrep`  |  pattern matching via regular expressions  |  `grep -inr PATTERN  FILES`  |
| `find `  |  search for files and file statuses  |  `find -L <location> -xtype l`  |
| `awk`  |   pattern scanning and processing language  |  `awk -Fsep '{print $0 $1 $2 ...}'`  |
| `sed`  |   stream editor for filtering and transforming text  | |
-----------------------------------------
