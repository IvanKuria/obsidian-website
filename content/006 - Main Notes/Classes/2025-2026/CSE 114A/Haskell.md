---
title: "Haskell"
type: lecture
class: CSE 114A
date: 2026-01-28
tags:
  - cs
  - programming-languages
---

# Functions, Types, let & where


## Functions

``` haskell
in_range min max x = 
	x >= min && x <= max
	
in_range 0 5 3
	=> True
	
in_range 4 5 3
	=> False
```

### Functions(let)
- the let keyword let's you store expressions in intermediary variables
``` haskell
in_range min max x = 
	let in_lower_bound = min <= x
		in_upper_bound = max >= x
	in
	in_lower_bound && in_upper_bound
```

### Functions(where)
``` haskell
in_range min max x = ilb && iub
where
	ilb = min <= x
	iub = max >= x
```

### Functions(if)

``` haskell
in_range min max x =
if ilb then iub else False
where
	ilb = min <= x
	iub max >= x 
```
## Types
``` haskell
x :: Integer
x = 1

y :: Bool
y = True

z :: Float
z = 3.1415
```

### Types(Functions)
``` haskell
in_range :: Integer -> Integer -> Integer -> Bool -- 3 Integer args, Bool ret
in_range min max x = 
	x >= min && x <= max
	
in_range 0.5 1.5 1 -- Type error
in_range 0 5 3 -- Correct
```
