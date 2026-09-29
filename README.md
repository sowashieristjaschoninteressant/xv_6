# xv6 | Operating System Extensions

This repository contains my extensions and experiments built on top of the **xv6 teaching operating system originally developed by MIT**.

> **Important:** The xv6 base operating system is **not my work**.  
> My contributions are the extensions and modifications described below.

## My Contributions

### System Calls

I extended xv6 with additional system calls, including:

- `clone()` — foundation for user-space threading
- `lseek()` — support for changing the current file offset
- `symlink()` — symbolic link support

These extensions required changes across the syscall interface, kernel implementation and user-space interface.

### User-Space Threading

Implemented basic threading support on top of the `clone()` system call.

The implementation includes:

- creation of threads sharing a process address space
- separate stacks for individual threads
- user-space abstractions around the underlying system call
- experiments with thread creation and execution

This project was primarily intended to better understand how threads can be implemented across the boundary between kernel and user space.

### User-Space Utilities / Library

Implemented and extended small user-space components for interacting with the new kernel functionality.

This includes wrappers and utilities used by the threading implementation and the additional system calls.

### File-System Extensions

Implemented additional file-system functionality, most notably:

- symbolic links via `symlink()`
- file-offset manipulation via `lseek()`

These changes involved working with xv6's inode, file-descriptor and system-call infrastructure.

### Disk / Partition Driver Experiments

Started work on extending the storage subsystem with support for disk partition handling.

This part is experimental and not intended to represent a complete production-ready partition driver.

## What I Worked With

Through these extensions I worked with operating-system concepts including:

- system-call implementation
- process and thread management
- virtual address spaces
- user/kernel boundaries
- stacks and process state
- file descriptors
- inode-based file systems
- storage and disk access
- synchronization and scheduling concepts
- low-level C programming

## Repository Structure

The repository contains both the original xv6 source code and my modified or experimental versions of individual components.

Because this repository originated as a university operating-systems project, it also contains intermediate files, experiments and different implementation variants.

The sections above describe the functionality that I personally implemented or extended.

## About xv6

xv6 is a small Unix-like teaching operating system originally developed at MIT for operating-systems education.

The original xv6 project and its base implementation belong to their respective authors at MIT.

Original project:

https://pdos.csail.mit.edu/6.828/2012/xv6.html

## Purpose

This repository documents my work with low-level operating-system development and was used to explore how kernel functionality, system calls and user-space abstractions interact.

The main focus of my modifications was gaining practical experience with **C, operating-system internals, system calls, threading and file-system functionality**.
