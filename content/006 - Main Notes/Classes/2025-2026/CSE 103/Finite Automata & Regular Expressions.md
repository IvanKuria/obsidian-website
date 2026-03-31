---
title: "Finite Automata & Regular Expressions"
type: lecture
class: CSE 103
date: 2026-01-20
tags:
  - cs
  - programming-languages
---

# Finite Automata & Regular Expressions

## Finite Automata

**Def**: A finite automaton $M$ is a 5 tuple(Q, $\sum$, $\delta$, $q_0$, $F$) 
- Q: finite set of states
- $\sum$: finite set of alphabet symbols
- $\delta$: transition function $\delta: Q \times \sum \rightarrow Q$ 
	- i.e. $\delta(q, a) = r$ means you are going from state q to state r via the symbol a
- $q_0$: start state
- $F$: set of accepted states

### Example
![[cse103-finite-automaton-example.png | 300]]

 #### Transition function
 ![[cse103-transition-function-table.png | 300]]

### Strings & Languages
- a [[string]] is a finite sequence of symbols $\sum$
- a [[language]] is a set of strings(finite or infinite) - in our case just finite $L$
- the [[empty string]] $\in$ is the string of length 0
- the [[empty language]] is $\emptyset$ is the set with no strings

### Acceptance
**Def**: $M$ accepts string $w = w_1w_2...w_n$ each $w_i \in \sum$ if there is a sequence of states $r_0, r_1, r_2, ..., r_n \in Q$ where:
- $r_0 = q_0$
- $r_i = \delta(r_{i - 1}, w_i)$ for $1 \leq i \leq n$ (*this means that to get the state $r_i$, we have to take the transition function of the previous state $r_{i - 1}$ and the current symbol $w_i$.*
- $r_n \in F$

### Regular Languages
**Def**: a language is regular if some finite automaton recognizes it. 

#### Operations
- **Regular operations**: Let $A$ and $B$ be languages:
- **Union**: $A \cup B$ = $\{w \mid w \in A \text{ or } w \in B\}$  which means the language is in either A or B
- **Concatenation**: $A \degree B = \{xy \mid x \in A \text{ and } y \in B\} = AB$ 
- **Star**: 

#### Closure Properties
**Theorem**: if $A_1, A_2$ are regular languages, so is $A_1 \cup A_2$ (closure under $\cup$)
**Proof**:  
Let $M_1 = (Q_1, \sum, \delta_1, q_1, F_1)$ recognize $A_1$
	$M_2 = (Q_2, \sum, \delta_2, q_2, F_2)$
Construct $M = (Q, \sum, \delta, q, F)$
M should accept input w if either $M_1$ or $M_2$ accept $w$.
![[cse103-closure-union-proof-diagram.png | 400]]

**Components of M**:
$Q = Q_1 \times Q_2$: *the set of states of $M$ is just the possible states of $M_1$ and $M_2$*
$= \{(q_1, q_1) \mid Q_1 \in Q_1 \text{ and } q_2 \in Q_2 \}$ 
$q_0 = (q_1, q_2)$: *the starting state of $M$ is the starting state of $M_1$and $M_2$*
$\delta((q, r), a) = (\delta_1(q_1, a_1), \delta_2(r, a))$: *the transition function of $M$is basically the transition functions of $M_1$ and $M_2$ since $M$ tracks the states of both. so to get the 'next state' of $M$ we need the next states of $M_1$ and M_2 $which$ is their transition functions*
$F = (F_1 \times Q_2) \cup (Q_1 \times F_2)$: *the final state of $M$ is the union of the 1. all possible states of the, final state of $M_1$ and any state from $M_2$. 2. all possible states of $M_1$ and the final state of $M_2$.* 

**Q**: riddle me this:
![[cse103-cartesian-product-states-quiz.png | 300]]

- the answer is C: because it's all possible combinations of states from $M_1$ and $M_2$
