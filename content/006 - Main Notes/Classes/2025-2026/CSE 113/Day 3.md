---
title: "Day 3"
type: lecture
class: CSE 113
date: 2026-01-14
tags:
  - cs
---

# Topic

## Core
- a core executes a stream of sequential ISA instructions
- a good mental model executes:
	- 1 ISA instruction per cycle
	- 3 Ghz means 3B cycles per second
	- 1 ISA instruction takes $.33$ ns
![[cse113-core-execution-model.png | 300]]

## Concurrency
*q*: what happens when multiple programs want to share the same core?
- this is called [[concurrency]]: multiple threads taking turns executing on the same hardware resource.

## Multicores
### Parallelism
- threads can execute simultaneously if there are enough resources
- this is also called concurrency but when they execute at the same time, it's called [[parallelism]] 
![[cse113-multicore-parallelism.png | 300]]

## Cores

![[cse113-core-architecture-diagram.png | 400]]
