
2024-08-22  13:00

Status: #child

Tags: [[Leetcode]] #leetcode #two-pointers #leetcode-medium [[Two Sum]]

# Two Sum II

### Code
```python
class Solution(object):

	def twoSum(self, numbers, target):
	"""
	:type numbers: List[int]
	:type target: int
	:rtype: List[int]
	"""
	# initializes the left and right pointers
	l, r = 0, len(numbers) - 1

	# sets up the loop
	while l < r:
		curSum = numbers[l] + numbers[r]
		if curSum > target:
			r-= 1
		elif curSum < target:
			l += 1
		else:
			return [l + 1, r + 1]
```

## Explanation
List: [1, 3, 4, 5, 7, 11] 
Target: 9

#### 1st Loop
- numbers[l] = 1
- numbers[r] = 11
- curSum = 12
- since the sum > target, we shift the right pointer to the left, essentially decreasing it(if curSum > target
#### 2nd Loop
- numbers[l] = 1
- numbers[r] = 7
- curSum = 8
- since the sum < target, we shift the left pointer to the right, essentially increasing it(if curSum < target

#### 3rd Loop
- numbers[l] = 3
- numbers[r] = 7
- curSum = 10
- since the sum > target, we shift the right pointer to the left, essentially decreasing it(if curSum > target

#### 4th Loop
- numbers[l] = 3
- numbers[r] = 5
- curSum = 8
- since the sum < target, we shift the left pointer to the right, essentially increasing it(if curSum < target

#### 5th Loop
 - numbers[l] = 4
- numbers[r] = 5
- curSum = 9
- return the indexes


## References
[Neetcode](https://www.youtube.com/watch?v=cQ1Oz4ckceM): 

