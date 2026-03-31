---
title: "Lecture 09"
type: lecture
class: CSE 130
date: 2025-05-01
tags:
  - cs
  - operating-systems
---

# Virtualization

## Client Server

### Benefits
- limit interactions to messages
- messages sent over "wire"
- more organized
- security
	- interaction limits security issues

### Downsides
- lots of separate modules to run on separate computers
- lots of overhead per computer(storage, memory, I/O connections)

## Virtualization
- allow several modules on one computer
- *not soft or hard modularity*
- *READ/WRITE* of one thread will not affect READ/WRITE of another thread  
- Separation can be relaxed  
	- IPC (inter-process communication) lets two processes READ/WRITE to the same physical address(es)  
	- But processes can write other processes’ (shared) memory
### Three Basic Virtualization Techniques

#### Multiplexing
- create multiple virtual objects from one underlying object
- i.e. *Virtual Memory*
![[cse130-virtualization-multiplexing.png | 200]]

#### Aggregation
- create one virtual object from multiple underlying objects
- i.e. *Content Delivery Network*
![[cse130-virtualization-aggregation.png | 200]]

#### Emulation
- create a new type of virtual object from underlying objects
- i.e. *ram disks*
![[cse130-virtualization-emulation.png | 200]]
