Class: [[CSE 114A]]
Subject: #computer-science #haskell 
Date: 2026-01-28
Teacher: **Prof. Miller

# Lists and Tuples

## Lists

``` haskell
[1, 2, 3, 4, 5] :: [Integer]
```

- lists can only contain elements of one type

### Generating a List

``` haskell
asc :: Int -> Int [Int]
asc n m
	m < n = []
	m == n = [m]
	m > n = n : asc (n + 1) m -- prepend n to the list, then call the generator recursively on n + 1 and m
	
asc 1 3
	=> [1, 2, 3]
```

### Functions
**length**: compute the length of a list
**(++)**: appending two lists
**(= =)**: checking if two lists are equal

``` haskell
length [1, 2, 3]
	=> 3
	
[1, 2] (++) [3, 4]
	=> [1, 2, 3, 4]
```