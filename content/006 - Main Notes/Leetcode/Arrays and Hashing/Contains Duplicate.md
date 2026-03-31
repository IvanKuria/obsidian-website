---
title: "Contains Duplicate"
type: problem
difficulty: easy
techniques:
  - arrays
date: 2024-10-11
maturity: growing
tags:
  - leetcode
  - cs
  - problem
---
**Topic:** [[Leetcode MOC]]


# [Contains Duplicate](https://leetcode.com/problems/contains-duplicate/)

```python
class Solution(object):
    def containsDuplicate(self, nums):
        """
        :type nums: List[int]
        :rtype: bool
        """

        seen = {}

        for num in nums:
            if num not in seen:
                seen[num] = 0
            else:
                return True
        return False
```

### Explanation
- The trick is to use a hash set(dictionary)
## References
[Neetcode](https://leetcode.com/problems/contains-duplicate/)

