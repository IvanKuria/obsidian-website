---
title: "Fruit Into Baskets"
type: problem
difficulty: medium
techniques:
  - two-pointers
  - arrays
  - hash-maps
  - strings
  - sliding-window
date: 2025-09-23
maturity: evergreen
tags:
  - leetcode
  - cs
  - problem
---
**Topic:** [[Leetcode MOC]]


# [Fruit Into Baskets](https://leetcode.com/problems/fruit-into-baskets/)

### Code

```python
from collections import defaultdict

class Solution(object):
    def totalFruit(self, fruits):
        """
        :type fruits: List[int]
        :rtype: int
        """

    
        count = defaultdict(int)
        res, l, total = 0, 0, 0
        n = len(fruits)

        for r in range(n):
            count[fruits[r]] += 1
            total += 1

            while len(count) > 2:
                left_fruit = fruits[l]
                count[left_fruit] -= 1
                total -= 1
                l += 1
            
                if not count[left_fruit]:
                    count.pop(left_fruit)

            
            res = max(res, total)
        
        return res
```

### Explanation
1. It uses a two pointer approach(sliding window). The problem wants us to find the longest contiguous subarray with 2 distinct elements
	
2. Use a sliding window with two pointers (l and r).
    
3. Expand r: add the fruit to count, increase window size.
    
4. If window has >2 types, shrink from l until only 2 remain.
    
5. Update res with the max window length.
    
6. Return res.
## References

[Neetcode](https://www.youtube.com/watch?v=yYtaV0G3mWQ)
