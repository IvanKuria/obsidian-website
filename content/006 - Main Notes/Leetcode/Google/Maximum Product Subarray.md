---
title: "Maximum Product Subarray"
type: problem
difficulty: medium
techniques:
  - dynamic-programming
date: 2025-09-20
maturity: evergreen
tags:
  - leetcode
  - cs
  - problem
---

# [Maximum Product Subarray](https://leetcode.com/problems/maximum-product-subarray/)

### Code

```python
class Solution(object):
    def maxProduct(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        res = max(nums)
        cur_max, cur_min = 1, 1

        for num in nums:
            if num == 0:
                cur_max, cur_min = 1, 1
                continue

            tmp = cur_max
            cur_max = max(num * cur_max, num * cur_min, num)
            cur_min = min(num * tmp, num * cur_min, num)
            res = max(res, cur_max, cur_min)
        return res
```

### Explanation
![[leetcode-maximum-product-subarray-explanation.png]]
- **Initialize**
    - `res = max(nums)` (best result seen so far)
    - `cur_max = cur_min = 1`
        
- **Iterate through nums**
    - If `num == 0`: reset `cur_max = cur_min = 1` (break in product chain).
    - Otherwise:
        - Store old `cur_max` in `tmp`.    
        - Update `cur_max = max(num, num*cur_max, num*cur_min)  
        - Update `cur_min = min(num, num*tmp, num*cur_min)`
            
- **Update result**
    - `res = max(res, cur_max)`
## References

[Neetcode](https://www.youtube.com/watch?v=lXVy6YWFcRM)
