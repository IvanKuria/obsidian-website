Class: [[CSE 113]]
Subject: #computer-science 
Date: 2026-01-14
Teacher: **Prof. Souza

# Topic

## Core
- a core executes a stream of sequential ISA instructions
- a good mental model executes:
	- 1 ISA instruction per cycle
	- 3 Ghz means 3B cycles per second
	- 1 ISA instruction takes $.33$ ns
![[Pasted image 20260114130233.png | 300]]

## Concurrency
*q*: what happens when multiple programs want to share the same core?
- this is called [[concurrency]]: multiple threads taking turns executing on the same hardware resource.

## Multicores
### Parallelism
- threads can execute simultaneously if there are enough resources
- this is also called concurrency but when they execute at the same time, it's called [[parallelism]] 
![[Pasted image 20260114130856.png | 300]]

## Cores

![[Pasted image 20260114131827.png | 400]]

