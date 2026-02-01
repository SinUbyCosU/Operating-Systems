# Operating Systems Lab

This repository contains operating systems coursework and lab assignments.

## Contents

### xv6_lab1
Contains shell implementation files:
- `sh.c` - Simplified xv6 shell implementation with support for pipes, redirection, and basic commands
- `t.sh` - Test script for shell functionality

### xv6-public
Full xv6 operating system source code - a simple Unix-like teaching operating system.

## xv6 Overview

xv6 is a re-implementation of Dennis Ritchie's and Ken Thompson's Unix Version 6 (v6). xv6 loosely follows the structure and style of v6, but is implemented for a modern RISC-V multiprocessor using ANSI C.

### Building and Running xv6

**Prerequisites:**
- GCC compiler
- QEMU emulator
- GDB debugger

**Build xv6:**
```bash
cd xv6-public
make
```

**Run xv6:**
```bash
make qemu
```

**Debug xv6 with GDB:**

Terminal 1:
```bash
cd xv6-public
make qemu-gdb
```

Terminal 2:
```bash
cd xv6-public
gdb
```

In GDB:
```
symbol-file kernel
target remote localhost:26000
br *0x0010000c
c
info reg
x/24x $esp
```

### Lab Assignments

#### Lab 1: Boot xv6
- Understand the boot process
- Set breakpoints and inspect stack
- Analyze bootloader behavior

**Key Tasks:**
1. Find the `_start` address: `nm kernel | grep _start`
2. Set breakpoint at kernel entry point
3. Inspect registers and stack contents
4. Identify stack initialization in `bootasm.S`
5. Analyze the call to `bootmain` and stack state

## Resources

- [xv6 Book](https://pdos.csail.mit.edu/6.828/2012/xv6/book-rev7.pdf)
- [MIT 6.828 Operating System Engineering](https://pdos.csail.mit.edu/6.828/)
- [xv6 Source Code](https://github.com/mit-pdos/xv6-public)

## Notes

- The shell implementation in `xv6_lab1/sh.c` demonstrates Unix-style command execution, pipes, and I/O redirection
- xv6 runs on QEMU, a versatile machine emulator and virtualizer
- GDB can be used to debug xv6 at the instruction level

## License

xv6 is inspired by John Lions's Commentary on UNIX 6th Edition (Peer to Peer Communications; ISBN: 1-57398-013-7). The xv6 sources are licensed under the traditional MIT license.
