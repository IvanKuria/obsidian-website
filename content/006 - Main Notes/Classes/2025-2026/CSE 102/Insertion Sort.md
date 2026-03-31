---
title: "Insertion Sort"
type: lecture
class: CSE 102
date: 2026-01-25
tags:
  - cs
  - algorithms
---

# Insertion Sort

## Code

**note**: the textbook has 1 being the '0' index
``` python
def insertion_sort(a, n)
	for i in range(2, n):
		key = a[i]
		# insert a[i] into the sorted subarray a[1: i - 1]
		j = i - 1
		while j > 0 and a[j] > key:
			a[j + 1] = a[j]
			j -= 1
		a[j + 1] = key
```

### Example
1. let's say we're given the array, $\{5, 2, 4, 6, 1, 3\}$ 

![[cse102-insertion-sort-example.png]]

## Loop Invariants
- elements in a[1: i - 1] are known as the [[loop invariant]] since these are always sorted. more formally:
	- *At the start of each iteration of the for loop of lines 1-8, the subarray a[1: i - 1] consists of the elements originally in a[1: i - 1], but in sorted order.*
- when using a loop invariant, you need to show three things:
	- **Initialization**: It is true prior to the first iteration of the loop.
	- **Maintenance**: If it is true before an iteration of the loop, it remains true before the next iteration.
	- **Termination**: The loop terminates, and when it terminates, the invariant, usually along with the reason that the loop terminated, gives us a useful property that helps show that the algorithm is correct

### Intialization
- We start by showing that the loop invariant holds before the first loop iteration, when $i = 2^2$ The subarray a[1: i - 1] consists of just the single element a[1], which is in fact the original element in a[1]. Moreover, this subarray is sorted (after all, how could a subarray with just one value not be sorted?), which shows that the loop invariant holds prior to the first iteration of the loop.

### Maintenance
- Informally, the body of the for loop works by moving the values in a[i - 1], a[i - 2], a[i - 3], and so on by one position to the right until it finds the proper position for a[i], at which point it inserts the value of a[i]. The subarray a[1: i] then consists of the elements originally in a[i : 1], but in sorted order. Incrementing i (increasing its value by 1) for the next iteration of the for loop then preserves the loop invariant.

### Termination

## Runtime Calculations
![[cse102-insertion-sort-runtime.png]]
