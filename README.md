# Operating_System
MIT 6.S081
## Intro 
This the Lecture, Resource and Lab project of MIT 6.S081 
https://pdos.csail.mit.edu/6.1810/,

https://pdos.csail.mit.edu/6.828/2022/schedule.html,

https://github.com/PeterHUistyping/Operating_System
## Set up submodule
```
git submodule update --init --recursive
```
https://github.com/PeterHUistyping/xv6-riscv/

# xv6 (Unix Version 6)
A re-implementation of Unix Version 6 (v6).  It is specially implemented for a modern RISC-V multiprocessor using ANSI C.
 
### 1. Unix util
```
git checkout util
```
**Reading**:
System call: fork, wait, exec, exit, cat, pipe (see xv6.pdf)<br/>
file descriptor dup <br/>
fork + close -> cat<br/>

Ctrl-p (ps), the kernel will print information about each process. <br/>

File System: inodes, dentry, softlink, file descriptors

i. **Implement** *sleep*<br/>
obtain the command-line arguments passed to a program<br/>
print an error message 
```
fprintf(2, "usage: grep pattern [file ...]\n");
exit(1)
```

ii. **Implement** *pingping*<br/>
1. Create two pipes for two-way communication:<br/> 
Otherwise, it will be received only by one side.
2. close the other side of the file descriptors.<br/> 
3. Transfer after receiving the message.
Otherwise, it will have output at the same time.
```
$ pingpong
34: :r erceeciveeid vpeidn gp
ong
```

iii. **Implement** *primes*<br/>
filter-and-pipeline <br/>
Need an iterative function. Create a pipe2, filter and write to the left side of pipe2. Then the right side of the pipe2 will be new iterative input to this function.


iv. **Implement** *find*<br/>
Using recursion to search inside the directory.
**Reading**:
System call: ls, passing in path<br/>
```
  struct dirent de;
  struct stat st;
```

v. **Implement** *args*<br/>
Read individual lines of input, a character at a time until a newline ('\n') appears.
```
echo hello too | xargs echo bye
```
### 2. System Call 
Using gdb/lldb

make qemu-gdb

**Reading**:
multiplexing, isolation, and interaction<br/>
Traps and system calls<br/>
The ecall instruction traps into the kernel and executes uservec, usertrap, and then syscall
**Implement** *Trace*<br/>
The trace system call should enable tracing for the process that calls it and any children that it subsequently forks, but should not affect other processes.
```
32 (1<<SYS_read) trace runs grep while tracing all system calls;
2147483647 (1<<31)  has all 31 low bits set.
```
 

 