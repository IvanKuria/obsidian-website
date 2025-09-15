Class: [[CSE 130]]
Subject: #computer-science #computer-systems 
Date: 2025-04-16
Teacher: **Dr. Veenstra

# Fundamental Abstractions in Computer Systems

## Tasks that a System Does
1. Store(essentially remember things)
	- i.e. **Memory
2. Compute things(Interpret)
	- i.e. **Interpreter
3. Communicate things
	- i.e. **Communication channels


# Memory

- relies upon *name* abstractions

## What are some memories
1. Registers
2. Cahces(L1, L2, L3)
3. DRAM
4. SSD's
5. HDD's
6. Tape Storage

![[Pasted image 20250416101405.png | 400]]

## Memory Properties
### Volatility
- Does the memory need power to be applied in order to remember?
- *The volatility/non-volatility split happens between DRAM and SSD's*

![[Pasted image 20250416101812.png | 400]]

- essentially the ones above the line require some sort of voltage/power source to sustain memory

### Abundance
- how much of the memory should we expect in a typical system?
- *less abundance as we move up in the hierarchy*

### Cost
- how expensive($/byte) is it?
- *more expensive as we move up in the hierarchy*

![[Pasted image 20250416102159.png | 400]]

### Performance
- [[bandwidth]]: how many units of memory can we get per unit of time?
- *higher performance at the top; lower performance at the bottom*

#### Two Measures
- bandwidth
	- i.e. *megabits per second*
- latency: how long does it take to get a single value from memory?
	- i.e. *nanoseconds*

##### Latency
- Lamport "Space-Time Diagrams"

![[Pasted image 20250416102906.png]]

*which is better; low read latency or low write latency?*
*answer*: low read latency because we can make writes asynchronous!

### Granularity
- what are the sizes of the values?
	- **registers(name/value map)
	- **bytes(Cache/RAM)
	- **block-Addressable(SSD/HDD)

#### Flash Memory
- Memory-cell tech makes writing complicated
	- *writing a 1*(called "erasing") must happen on an entire bank
	- *writing a 0*(called "programming") can happen on an individual bit
- NOR Flash memory *reads words*
- NAND Flash memory *reads pages

### Failure Rate

#### Block Devices
- these fail frequently

#### DRAM
- fails less frequently

#### RAM
- rarely fail
- most systems ignore the failures since fixing them would be expensive!
      