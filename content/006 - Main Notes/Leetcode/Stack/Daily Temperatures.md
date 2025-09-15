
2024-08-26  17:18

Status: #child

Tags:  [[Leetcode]] #stack #leetcode #leetcode-medium [[Daily Temperatures]] [[Min Stack]] [[Valid Parentheses]]

# [Daily Temperatures](https://leetcode.com/problems/daily-temperatures/)

### Code

```python
class Solution(object):
	def dailyTemperatures(self, temperatures):	
		"""		
		:type temperatures: List[int]		
		:rtype: List[int]		
		"""
		
		res = [0] * len(temperatures)		
		stack = [] # pair: [temp, index]
				
		for x, temp in enumerate(temperatures):
			# if the stack:
			# 1. Isn't empty
			# 2. The current temp > temp in stack		
			while stack and temp > stack[-1][0]:
				# sets variables equal to the temp and index of the
				# popped pair			
				stackTemp, stackIndex = stack.pop()	

				# sets res = the difference between their indexes to get 
				# how long
				res[stackIndex] = (x - stackIndex)				
				stack.append([temp, x])
		
		return res
```


## References
[Neetcode](https://leetcode.com/problems/daily-temperatures/)

