---
title: "Find the Highest Altitude"
type: problem
difficulty: easy
techniques:
  - strings
date: 2025-09-22
maturity: evergreen
tags:
  - leetcode
  - cs
  - problem
---
**Topic:** [[Leetcode MOC]]


# [Find the Highest Altitude](https://leetcode.com/problems/find-the-highest-altitude/)

### Code

```python
class Solution(object):
    def largestAltitude(self, gain):
        """
        :type gain: List[int]
        :rtype: int
        """
        
        '''
        0 - 1: -5
        1 - 2: 1
        2 - 3: 5
        3 - 4: 0
        4 - 5: -7


        '''
        max_height, cur_height = 0, 0

        for g in gain:
            cur_height += g
            max_height = max(max_height, cur_height)

        return max_height
```

### Explanation
1. We need to keep track of the current height, and max height
2. Iterate through the array, calculate current height, and set max height equal to the max between max height and cur height
3. Return max height

## References

Me
