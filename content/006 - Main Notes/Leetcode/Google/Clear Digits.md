---
title: "Clear Digits"
type: problem
difficulty: easy
techniques:
  - arrays
  - strings
date: 2025-09-22
maturity: evergreen
tags:
  - leetcode
  - cs
  - problem
---

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
