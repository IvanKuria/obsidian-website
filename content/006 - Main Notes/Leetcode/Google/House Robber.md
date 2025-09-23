
2025-09-22  22:27

Status: #adult

Tags: #leetcode #leetcode-medium #dynamic-programming #google [[Leetcode]]

# [House Robber](https://leetcode.com/problems/house-robber/)

### Code

```python
class Solution(object):
    def rob(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        
        n = len(nums)
        if n == 1:
            return nums[0]
        
        if n == 2:
            return max(nums[0], nums[1])

        prev = nums[0]
        cur = max(nums[0], nums[1])

        for i in range(2, n):
            prev, cur = cur, max(nums[i] + prev, cur)
        
        return cur
```

### Explanation
1. We have 2 base case:
	1. if the length of the array is 1, just return the only element
	2. If the length of the array is 2, return the max of the 2 elements
2. To understand our next approach, analyze this photo![[Pasted image 20250922223341.png | 400]]
3. Let's look at the 3 index since we have accounted for the edge cases. If we choose to rob 10, we have to also add the money from 2 steps back because we can't rob adjacent houses = $10 + 5 = 15$. 
4. Also we can not rob and just keep the 10. In this case robbing is better because $15 > 10$. 
5. We repeat this until we reach the end
6. We can use memoization and have a dp array with the same length as the input array, initialized all to 0's. i.e. dp = [0, 0, 0, 0, 0, 0, 0]
7. A clever trick to save space is to use a prev and cur variable.
8. prev is set to nums[0] and cur = max(nums[0], nums[1]). 
	1. Iterate from 2 to n(length of nums)
	2. prev = cur and cur = max(nums[i] + prev(which is from 2 steps back), cur)
	3. return cur
## References

[Greg Hogg](https://www.youtube.com/watch?v=kIII1uT6F8Y)