Class: [[CSE 130]]
Subject: #computer-science #computer-systems 
Date: 2025-04-03
Teacher: **Dr. Veenstra

# Chapter 1

## What is a System?

- it's a set of interconnected components that has an expected behavior observed at the interface with it's environment.

## Complexity

### 4 Issues of Complexity

#### Emergent Properties
- properties that show up only when combining individual components
- often it is used in a negative context. i.e *The Millenium Bridge, London*

#### Propagation of Effects
- problems in one component affect other components. i.e [*Northeast Blackout of 1965*](https://en.wikipedia.org/wiki/Northeast_blackout_of_1965)

#### Not proportional(incommensurate) Scaling
- not all parts of a system scale at the same rate 

#### Tradeoffs
- what will I need to sacrifice for more of something else

### 4 Signs of Complexity

1. Large number of *components*
2. Large number of *interconnections*
3. Lots of *irregularities*
4. Long description(*high information content*)

### Sources of Complexity
#### 1. Interactions of requirements
- A general purpose tool that can do $X$ and other things is more complex than a special purpose tool that can only do $X$
- general purpose tool
![[Pasted image 20250403103739.png | 400]]
- special purpose tool
![[Pasted image 20250403103824.png | 400]]

#### 2. Increasing efficiency, utilization, or other measure of "goodness"
- i.e. car engines
	- *1960 Chevy*(simple)
		- burn gasoline, get mechanical power
	- *2015 Honda CR-V*(much more complex)
		- adds: more efficient, lower emissions(better for the environment), more durable


### What increase complexity

#### Principle of escalating complexity
- adding a requirement increases complexity out of proportion
- i.e. adding a cache requires doubling the implementation

#### Principle of excessive generality
- pretty self-explanatory