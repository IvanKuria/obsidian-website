
2024-10-07  17:23

Status:

Tags: [[Leetcode]] [[Binary Search]] #two-pointers #leetcode-medium 

# [Koko Eating Bananas](https://leetcode.com/problems/koko-eating-bananas/)

### Code

```python
class Solution(object)
    def minEatingSpeed(self, piles, h):
        """
        :type piles: List[int]
        :type h: int
        :rtype: int
        """
  
        l, r = 1, max(piles)
        res = r
  
        while l <= r:
            k = (l + r) // 2
            totalTime = 0
  
            for p in piles:
                totalTime += math.ceil(float(p) / k)
            if totalTime <= h:
                res = k
                r = k - 1
            else:
                l = k + 1

        return res
```



## References

