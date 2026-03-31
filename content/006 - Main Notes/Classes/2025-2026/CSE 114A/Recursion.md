---
title: "Recursion"
type: lecture
class: CSE 114A
date: 2026-01-28
tags:
  - cs
  - programming-languages
---

# Recursion, Guards, Patterns

## Recursion
- let's use factorial as an example

``` haskell
fac n = 
	if n <= 1 then
		1
	else
		n * fac (n - 1)
```

## Guards
- if then else is just one way, guards do something similar
- guards must have some sort of boolean expression

``` haskell
fac n
	n <= 1 = 1
	otherwise n * fac (n - 1)
```
