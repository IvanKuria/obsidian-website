
2024-08-22  15:32

Status: #baby 

Tags:  [[Leetcode]] #leetcode #two-pointers #leetcode-medium [[Two Sum]]

# Container with Most Water

### Code
```python
class Solution(object):
	def maxArea(self, height):
	"""	
	:type height: List[int]
	:rtype: int
	"""
	res = 0
	#initalize the pointers
	l, r = 0, len(height) - 1
		
	while l < r:
		area = (r - l) * min(height[l], height[r])  # sets the area
		res = max(area, res)                        # find the max of area                                                        & res
		if height[l] < height[r]:
			l += 1
		else:
			r -= 1
	
	return res
```




## References
[Neetocode](https://youtu.be/UuiTKBwPgAo)
