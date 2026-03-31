---
title: "Min Stack"
type: problem
difficulty: medium
techniques:
  - stack
date: 2024-08-23
maturity: growing
tags:
  - leetcode
  - cs
  - problem
---
**Topic:** [[Leetcode MOC]]


# Min Stack

### Code
```python
class MinStack(object):

	def __init__(self):
		self.stack = []
		self.minStack = []
		
	  
	
	def push(self, val):
		"""
		:type val: int	
		:rtype: None	
		"""	
		self.stack.append(val)	
		minVal = min(val, self.minStack[-1] if self.minStack else val)	
		self.minStack.append(minVal)
		
	
	def pop(self):	
		"""	
		:rtype: None	
		"""	
		self.stack.pop()	
		self.minStack.pop()	
	  
	
	def top(self):
		"""
		:rtype: int	
		"""	
		return self.stack[-1]	
	  
	
	def getMin(self):	
		"""	
		:rtype: int	
		"""	
		return self.minStack[-1]

# Your MinStack object will be instantiated and called as such:

# obj = MinStack()

# obj.push(val)

# obj.pop()

# param_3 = obj.top()

# param_4 = obj.getMin()
```


### Note
- the getMin() function must run in O(1) time

## References
[Neetcode](https://youtu.be/qkLl7nAwDPo)

