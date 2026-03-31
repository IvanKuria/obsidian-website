---
title: "Day 3"
type: lecture
class: CSE 114A
date: 2026-01-12
tags:
  - cs
  - programming-languages
---

# Lambda Calculus

## Syntax of terms

$\lambda x \rightarrow x$: this is an identity function. 
- i.e. $(\lambda x \rightarrow x) 114 \Rightarrow 114$

## Notation
### Alpha Equivalence
1. **e[x := 5]** means to replace all free occurrences of x with v in e
2. $\alpha$ equivalence 
	1. You can rename parameters. i.e
		$\lambda x \rightarrow x \Rightarrow \alpha$ $\lambda y \rightarrow y$
		$\lambda f \rightarrow f(\lambda z \rightarrow z)$ $\Rightarrow \alpha$ $\lambda f \rightarrow f(\lambda w \rightarrow w)$

### Beta Reduction
$(\lambda x \rightarrow e)$ v $\Rightarrow \beta$ $e[x : = v]$

#### Example
$(\lambda x y \rightarrow x)$ 1 2
= $((\lambda x \rightarrow \lambda y \rightarrow x) 1) 2$
$\Rightarrow \beta$ $\lambda y \rightarrow x [x := 1] 2$
= $(\lambda y \rightarrow 1) 2$
$\Rightarrow \beta$ 1[y := 2]
= 1

**Terminology**: 
- $(\lambda x \rightarrow e)$ v is called a **$\beta$-redex**(reducible expression)
- An expression is **normalized** if it has no redexes

*Question*: is this normlized? $(\lambda y \rightarrow (\lambda x \rightarrow x) y)$ 114
