---
title: "Pushdown Automata, Conversion of CFG to PDA and Reverse Conversion"
type: lecture
class: CSE 103
date: 2026-02-04
tags:
  - cs
  - programming-languages
---

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
![[cse103-cfg-example.png]]

## Ambiguity
![[cse103-ambiguous-cfg-comparison.png]]
- both $G_2$ and $G_3$ recognize the same language, i.e. $L(G_2) = L(G_3)$. 
- However, $G_2$ is an ambiguous CFG and $G_3$ is ambiguous
- This is what the parse tree for $G_3$ would look like:
	- ![[cse103-parse-tree-example.png | 200]]
