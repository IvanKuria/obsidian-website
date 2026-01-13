Class: [[CSE 114A]]
Subject: #computer-science 
Date: 2026-01-12
Teacher: **Prof. Miller

# Lambda Calculus Cont.

## Definitions

### Bindings
[[Bindings]]: are associations of parameters to variables. We say a **variable** occurrence is bound if it's part of a binding and otherwise it's free. (only **variables** can be bound)

#### Example
$\lambda x y \rightarrow f x y$ - $x$ and $y$ are bound and $f$ is free

### Scope
Scope: the scope of a parameter is everywhere a variable could be bound to it. 
i.e. $\lambda x \rightarrow \lambda y \rightarrow f x y$
	- scope of y:  $x y$
	- scope of x: $\lambda y \rightarrow f x y$

## Computing Set of Free Variables

- $FV(e)$ is the set of free variables in e ,recursively defined by:
	- $FV(x)$ = {x}: *if x is a variable*
	- $FV(a, b) = FV(a) \cup FV(b)$: *if a and b are expressions*
	- $FV(\lambda x \rightarrow e) = FV(e) - \{x\}$

#### Example
![[Pasted image 20260112221053.png]]

### Closed
- An expression $e$ is [[closed]] if $FV(e) = \{\}$ (i.e. it has no free variables)

##### Example
*q*: *closed* or *not closed*
1. $\lambda x \rightarrow x$: *closed*
2. $\lambda x \rightarrow x y$: *not closed*