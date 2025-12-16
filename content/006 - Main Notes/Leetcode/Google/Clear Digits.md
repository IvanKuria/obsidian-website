
2025-09-22  17:10

Status: #adult

Tags: #leetcode #leetcode-easy #google #strings #arrays [[Removing Stars From a String]] [[Leetcode]]

# [Clear Digits](https://leetcode.com/problems/clear-digits/)

### Code

```python
class Solution(object):
    def clearDigits(self, s):
        """
        :type s: str
        :rtype: str
        """


        stack = []

        for char in s:
            if not char.isdigit():
                stack.append(char)
            else:
                stack.pop()
        
        return "".join(stack)
```

### Explanation
1. Just like ![[Removing Stars From a String]] except it's digits instead of stars.
## References

Me