---
title: "Jewels  and Stones"
type: problem
difficulty: easy
techniques:
  - strings
date: 2025-08-13
maturity: growing
tags:
  - leetcode
  - cs
  - problem
---
**Topic:** [[Leetcode MOC]] | [[Complexity Cheat Sheet]]


# [Jewels and Stones](https://leetcode.com/problems/jewels-and-stones/)

### Code

```python
class Solution(object):
    def numJewelsInStones(self, jewels, stones):
        """
        :type jewels: str
        :type stones: str
        :rtype: int
        """
        
        jewels_set = set(jewels)
        return sum(s in jewels_set for s in stones)
```


## References

1. Essentially what we want to do is convert `jewels` into a set for O(1) look-ups
2. Then compare each element in `stones` to each element in the `jewels` set and return the sum for matching elements

## Complexity

**Time**: O(n)
**Space**: O(1) since alphabet size is fixed
