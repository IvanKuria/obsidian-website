
2025-09-20  12:00

Status:

Tags: #leetcode #leetcode-medium #google #backtrack [[Leetcode]] [[Backtracking Intro]] #computer-science 

# [Generate Parentheses](https://leetcode.com/problems/generate-parentheses/)

### Code

```python
class Solution(object):
    def generateParenthesis(self, n):
        """
        :type n: int
        :rtype: List[str]
        """
        
        res, sol = [], []

        def backtrack(openn, close):
            # base case
            if len(sol) == 2 * n:
                res.append("".join(sol))
                return
			
			# 
            if openn < n:
                sol.append("(")
                backtrack(openn + 1, close)
                sol.pop()

            if close < openn:
                sol.append(")")
                backtrack(openn, close + 1)
                sol.pop()

        backtrack(0, 0)
        return res
```

### Explanation
1. Initialize res and sol to empty lists
2. The backtracking function, `backtrack(openn, close)`,  will make 3 checks:
	1. **Base case**: once we reach the leaf nodes(`len(sol) = 2 x n`), append the joined strings to res
	2. If the number of closing brackets is less than n, append '(', call backtrack(openn + 1, close) and then pop
	3. If the number of closing brackets is less than the number of opening brackets, do the same for opening except use a closing bracket
3. Call backtrack(0, 0) and return res
## References

[Greg Hogg](https://www.youtube.com/watch?v=oC4saZRNwfI)
