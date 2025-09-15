Class: [[CSE 130]]
Subject: #computer-science #computer-systems 
Date: 2025-05-01
Teacher: **Dr. Veenstra 

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
![[Pasted image 20250501194303.png | 200]]

#### Aggregation
- create one virtual object from multiple underlying objects
- i.e. *Content Delivery Network*
![[Pasted image 20250501194430.png | 200]]

#### Emulation
- create a new type of virtual object from underlying objects
- i.e. *ram disks*
![[Pasted image 20250501194659.png | 200]]



