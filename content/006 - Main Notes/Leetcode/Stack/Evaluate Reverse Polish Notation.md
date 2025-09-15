
2024-08-26  17:01

Status: #child 

Tags: [[Leetcode]] #leetcode #leetcode-medium #stack [[Min Stack]] [[Valid Parentheses]]

# [Evaluate Reverse Polish Notation](https://leetcode.com/problems/evaluate-reverse-polish-notation/)

### Code
```python
class Solution(object):

	def evalRPN(self, tokens):	
		"""		
		:type tokens: List[str]		
		:rtype: int		
		"""		
		stack = []

		for char in tokens:		
			if char == "+":			
				stack.append(stack.pop() + stack.pop())			
			elif char == "-":			
				a, b = stack.pop(), stack.pop()			
				stack.append(b - a)			
			elif char == "*":			
				stack.append(stack.pop() * stack.pop())			
			elif char == "/":			
				a, b = stack.pop(), stack.pop()				
				stack.append(int(float(b) / a))		
			else:
				stack.append(int(char))
		
		return stack[0]
```

### Explanation
1. **Initialize an empty stack**.
2. **Iterate through each token** in the RPN expression:
    - If the token is an operator, pop the necessary number of operands from the stack, perform the operation, and push the result back onto the stack.
    - If the token is a number, convert it into an integer and push it onto the stack.
3. **Return the result**, which is the only element left in the stack after processing all tokens.

## References
[Neetcode](https://leetcode.com/problems/evaluate-reverse-polish-notation/)
