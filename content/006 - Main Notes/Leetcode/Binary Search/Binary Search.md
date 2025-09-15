
2024-09-03  21:23

Status: #child

Tags: [[Leetcode]] #binary-search #leetcode #leetcode-easy #two-pointers 

# [Binary Search](https://leetcode.com/problems/binary-search/)

### Code
```python
class Solution(object):

	def search(self, nums, target):
	
		"""		
		:type nums: List[int]		
		:type target: int		
		:rtype: int		
		"""

		l, r = 0, len(nums) - 1

		while l <= r:		
			m = (l + r) // 2			
			if nums[m] > target:			
				r = m - 1			
			elif nums[m] < target:			
				l = m + 1			
			else:			
				return m
		
		return -1
```


### Explanation
- essentially we are searching for a target num by parsing through a sorted array by looking at the midpoint and moving the right and left pointers accordingly.

## References
[Neetcode](https://youtu.be/s4DPM8ct1pI)

