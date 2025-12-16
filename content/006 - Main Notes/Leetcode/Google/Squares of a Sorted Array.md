
2025-09-22  19:06

Status: #adult

Tags: #leetcode #leetcode-easy #two-pointers #google [[Leetcode]]

# [Squares of a Sorted Array](https://leetcode.com/problems/squares-of-a-sorted-array/)

### Code

```python
import heapq

class Solution(object):
    def sortedSquares(self, nums):
        """
        :type nums: List[int]
        :rtype: List[int]
        """

        res = []
        l, r = 0, len(nums) - 1

        while l <= r:
            if abs(nums[r]) > abs(nums[l]):
                res.append(nums[r] ** 2)
                r -= 1
                
            else:
                res.append(nums[l] ** 2)
                l += 1
        
        return res[::-1]
```

### Explanation
1. Since this is sorted in increasing order, we can use two pointers, one on the left and right.
2. We check if the abs(nums[r]) > abs(nums[l]), and move the right pointer to the left and vice versa for the left.
3. The result list will be in decreasing order so all we need to do is reverse it at the end
## References

[Greg Hogg](https://www.youtube.com/watch?v=z0InhrjK3es)