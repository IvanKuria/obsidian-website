
2024-08-23  21:06

Status: #child

Tags: [[Leetcode]] #stack #leetcode #leetcode-easy 

# [Valid Parentheses](https://leetcode.com/problems/valid-parentheses/)

### Code
```python
class Solution(object):

	def isValid(self, s):
		"""
		:type s: str
		:rtype: bool
		"""
		
		stack = []
		
		available = {
		")":"(",
		"}":"{",
		"]":"["
		}
		
		for bracket in s:
			if bracket in available:  # if it's a closing bracket
		
				# remove the last element in the stack if the stack: 
				# 1. isn't empty
				# 2. if the last element in the stack = a closing bracket
				if stack and stack[-1] == available[bracket]:
					stack.pop()
				else:
					return False
			# this means the bracket is an opening bracket
			else:
				stack.append[bracket]
		return True if not stack else return False
			 
```



## References
[Neetcode](https://youtu.be/WTzjTskDFMg)

