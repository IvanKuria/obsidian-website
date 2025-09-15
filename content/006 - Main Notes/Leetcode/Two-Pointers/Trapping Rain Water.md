
2024-08-22  21:32

Status: #child  

Tags: [[Leetcode]] #leetcode #leetcode-hard #two-pointers 

# [Trapping Rain Water](https://leetcode.com/problems/trapping-rain-water/)


### My Code(Time Limit Exceeded)
 - it works but it's slow
 
```python
class Solution(object):
	def trap(self, height):
	"""
	:type height: List[int]
	:rtype: int
	"""
	
		res = 0
		for x in range(len(height)):
			lower = height[0:x]
			upper = height[x:]
			
			if not lower or not upper:
				continue
			
			max_lower = max(lower)
			max_upper = max(upper)
			unit = min(max_lower, max_upper) - height[x]
			
			if unit > 0:
				res += unit
				
		return res
```


### Code that Works
```python
class Solution(object):
	def trap(self, height):
	"""
	:type height: List[int]
	:rtype: int
	"""
	
		if not height: return 0
		l, r = 0, len(height) - 1
		leftMax, rightMax = height[l], height[r]
		res = 0
		
		while l < r:
			if leftMax < rightMax:
				l += 1
				leftMax = max(leftMax, height[l])
				res += leftMax - height[l]
			else:
				r -= 1
				rightMax = max(rightMax, height[r])
				res += rightMax - height[r]
		return res
```
## References
[Neetcode](https://youtu.be/ZI2z5pq0TqA)
