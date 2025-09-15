
2024-08-22  12:39

Status: #baby

Tags: [[Leetcode]] #two-pointers #leetcode #leetcode-easy 


# Two Sum
### Code
```python
class Solution(object):

	def twoSum(self, numbers, target):
	
	"""
	:type numbers: List[int]
	:type target: int
	:rtype: List[int]
	"""
	seen = {}
	
	for i, num in enumerate(numbers):
		goal = target - num
		if goal not in seen:
			seen[num] = i
		else:
			return [seen[goal] + 1, i + 1]
```

### Explanation
 - Iterate through the array using enumerate to store the indexes for later

## References

