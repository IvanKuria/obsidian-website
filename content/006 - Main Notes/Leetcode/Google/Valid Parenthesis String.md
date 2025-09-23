
2025-09-22  22:42

Status: #adult 

Tags: #leetcode #leetcode-medium #dynamic-programming #google [[Leetcode]]

# [Valid Parenthesis String](https://leetcode.com/problems/valid-parenthesis-string/)

### Code

```python
class Solution(object):
    def checkValidString(self, s):
        """
        :type s: str
        :rtype: bool
        """
        
        left_max, left_min = 0, 0

        for char in s:
            if char == "(":
                left_max, left_min = left_max + 1, left_min + 1
            elif char == ")":
                left_max, left_min = left_max - 1, left_min - 1
            else:
                left_max, left_min = left_max + 1, left_min - 1
            if left_max < 0:
                return False
            if left_min < 0:
                left_min = 0
        
        return left_min == 0
```

### Explanation
1. Keep track of a range of possible open ( counts:
    - left_max = max possible opens
    - left_min = min possible opens
    
2. For each char:
    - ( → both +1
    - ) → both –1
    - * → could be ( or ) or empty → left_max +1, left_min –1
    
3. If left_max < 0 → too many ) → invalid.
    If left_min < 0, clamp to 0 (means we had extra flexibility).
    
4. At the end, valid if left_min == 0 (we can balance everything).

**Key idea:** * expands the range. As long as 0 stays in the range at the end, the string can be valid.

## References

