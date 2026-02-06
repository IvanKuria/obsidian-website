Class: [[CSE 103]]
Subject: #computer-science 
Date: 2026-02-04
Teacher: **Prof. 

# Pushdown Automata, Conversion of CFG to PDA and Reverse Conversion

## CFG
**Def**: a context free grammar(CGF) $G$ is a 4-tuple($V, \sum, R, S$)
- $V$: finite set of variables
- $\sum$: finite set of terminal symbols
- $R$: finite set of rules(rule form $V \rightarrow (V \cup \sum)^*$)
- $S$: start variable

For $u, v \in (V \cup \sum)$ write:
1. $u \Rightarrow v$ if can go from $u$ to v $with$ one substitution step in $G$
2. $u \Rightarrow ^ * v$ if can go from u to v with some number of substitution steps in G


### Example
![[Pasted image 20260204091120.png]]

## Ambiguity
![[Pasted image 20260204091552.png]]
- both $G_2$ and $G_3$ recognize the same language, i.e. $L(G_2) = L(G_3)$. 
- However, $G_2$ is an ambiguous CFG and $G_3$ is ambiguous
- This is what the parse tree for $G_3$ would look like:
	- ![[Pasted image 20260204091748.png | 200]]

