
2024-10-11  21:30

Status:

Tags: [[Leetcode]]

# [Valid Anagram](https://leetcode.com/problems/valid-anagram/)

```python
class Solution(object):
    def isAnagram(self, s, t):
        """
        :type s: str
        :type t: str
        :rtype: bool
        """
        return sorted(s) == sorted(t)
```

### Explanation
- Just use sorted() on both arrays
## References
[Neetcode](https://leetcode.com/problems/valid-anagram/)
