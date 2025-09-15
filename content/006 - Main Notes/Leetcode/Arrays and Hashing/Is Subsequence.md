
2025-08-11  14:09

Status: #child

Tags: #leetcode #leetcode-easy #strings

# [Is Subsequence](https://leetcode.com/problems/is-subsequence/)

### Code

```python
class Solution(object):
    def isSubsequence(self, s, t):
        """
        :type s: str
        :type t: str
        :rtype: bool
        """
        
		""" edge cases """
        if len(s) > len(t):
            return False
        if len(s) == 0:
            return True
            
        count = 0
        r = 0

        for letter in s:
            while r < len(t):
                if t[r] == letter:
                    r += 1
                    count += 1
                    break
                r += 1
            
        return False if count < len(s) else True
```


## References

Me hehe