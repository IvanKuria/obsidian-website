
2025-09-19  12:14

Status: #adult

Tags: #leetcode #leetcode-medium #google #strings [[Leetcode]]

# [Maximum Subarray](https://leetcode.com/problems/maximum-subarray/)

### Code

```python
class Solution(object):
    def maxSubArray(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        
        cur_sum, max_sum = 0, float("-inf")

        for i in range(len(nums)):
            cur_sum += nums[i]
            max_sum = max(max_sum, cur_sum)

            if cur_sum < 0:
                cur_sum = 0

        return max_sum
```

### Explanation
1. This approach uses **Kadane's Algorithm**
2. We keep track of the cur and max sum.
3. As we traverse the array, we add to cur_sum, nums[i] and calculate max_sum.
4. If cur_sum ever drops below 0, then we can set it back to 0
5. The trick here is to make sure to set max_sum initially to $-inf$
## References

[Greg Hogg](https://www.youtube.com/watch?v=hLPkqd60-28)