
2025-09-18  21:36

Status: #adult

Tags: #leetcode #leetcode-easy #computer-science #dynamic-programming [[Leetcode]] 

# [Climbing Stairs](https://leetcode.com/problems/climbing-stairs/)

### Code

```python
class Solution(object):
    def climbStairs(self, n):
        """
        :type n: int
        :rtype: int
        """
        
        # base cases
        if n == 1: return 1
        if n == 2: return 2

        prev = 1
        cur = 2

        for i in range(2, n):
            prev, cur = cur, cur + prev
            
        return cur
        
        # Time: O(n)
        # Space: O(1)
```

### Explanation
1. This is very similar to Fibonacci. 
2. We handle the base cases where n = 1 and n = 2
3. Then we set prev = 1 and cur = 2.
4. Iterate from 2, n and set prev = cur and cur = prev + cur
5. Return and you're done.

#### Example
1. Let's say $n = 4$:
	1. **$1^{st}$ iteration**: prev = 2, cur = 3, 
	2. $2^{nd}$ **iteration**: prev = 3, cur = 5
	3. **Return**: $5$ for $4$ steps

## References
[Greg Hogg](https://www.youtube.com/watch?v=I-R1XsECJu8)
