
2024-12-20  17:34

Status: #child #leetcode #leetcode-medium 

Tags: #stack #arrays [[Leetcode]]

# [Removing Stars From a String](https://leetcode.com/problems/removing-stars-from-a-string/)

### Code

```python
class Solution(object):
    def removeStars(self, s):
        """
        :type s: str
        :rtype: str
        """

        stack = []

        for letter in s:
            if letter != "*":
                stack.append(letter)
            else:
                stack.pop(-1)
        return "".join(stack)
        
    # Time Complexity: O(n)
    # Space Complexitty: O(n)
```

### Explanation
- way to simple don't even need to explain
## References

