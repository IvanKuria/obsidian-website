Class: [[CSE 102]]
Subject: #computer-science 
Date: 2026-01-07
Teacher: **Prof. Bailey

#  Sorting

## Insertion Sort

``` python
def insert_sort(m):
	for i in range(2, m):                              # c1 m
		key = A[i]                                     # c2 m - 1
		# insert A[i] into sorted A[1: i - 1]
		
		j = i - 1.                                     # c1 m - 1
		while j > 0 and A[j] > key:                    
			A[j + 1] = A[j]
			j -= 1
			
		A[j + 1] = key
```

$$ T(m) = c_1m  + c_2(m - 1) + c_4(m - 1) + c_5 \sum_{i = 1}^{m}{t_i} + c_6 \sum_{i = 1}^{m}{t_i - 1}  + c_7 \sum_{i = 1}^{m}{t_i - 1} + c_8(m - 1)$$
= 
$$(c_1 + c_2 + c_4 + c_5  + c_8)m - (c_2 + c_4 + c_5 + c_8) = am + \lambda$$
### Worst Case 

$$T(m) = ( \frac{c_5}{2} + \frac{c_2}{2} + (c_1 + c_2 + c_4 + \frac{c_7}{2})m^2 + (\frac{c_5}{2} - \frac{c_6}{2} - \frac{c_7}{2} + c_5)$$
$$ = am^2 + \lambda m + c$$
$$= \theta (m^2)$$

## Divide and Conquer
- divide problem into one or more subsequences