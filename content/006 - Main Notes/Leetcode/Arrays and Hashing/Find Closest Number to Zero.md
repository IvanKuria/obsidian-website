
2025-08-11  13:51

Status: #child

Tags: #arrays #strings #leetcode #leetcode-easy [[Leetcode]]

# [Find Closest Number to Zero](https://leetcode.com/problems/find-closest-number-to-zero/)

### Code

```python
class Solution(object):
    def findClosestNumber(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        closest = nums[0]
        
        for x in nums:
            if abs(x) < abs(closest):
                closest = x
        
        if closest < 0 and abs(closest) in nums:
            return abs(closest)
        else:
            return closest
```

## References

[AlgoMap](https://www.youtube.com/watch?v=dLlKA5DQKYs)