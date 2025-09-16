
2025-09-16  10:01

Status: #adult

Tags: #leetcode #leetcode-medium [[Leetcode]] [[Backtracking Intro]] [[Subsets]]

# [Subsets II](https://leetcode.com/problems/subsets-ii/)

### Code

```python
class Solution(object):
    def subsetsWithDup(self, nums):
        """
        :type nums: List[int]
        :rtype: List[List[int]]
        """

        # backtracking problem 

        res, sol = [], []
        nums.sort()
        n = len(nums)

        def backtrack(i):
            # base case
            if i == n:
                res.append(sol[:])
                return

            # include nums[i]
            sol.append(nums[i])
            backtrack(i + 1)
            sol.pop()

            # not include nums[i]
            while i + 1 < n and nums[i] == nums[i + 1]:
                i += 1

            backtrack(i + 1)
        
        backtrack(0
```

- **Time complexity**: $O(n∗2^ n)$
- **Space complexity**:
    - $O(n)$ extra space.
    - $O(2n)$ space for the output list.
### Explanation
1. Very similar to [[Subsets]] but since there are duplicates, we have to sort nums first
2. **Base case**: if the index = length of nums
3. **Choices**:
	1. *Include nums[i]*: append, backtrack, pop
	2. *Not include nums[i]*: 2 conditions we have to check:
		1. since there are duplicates, we need to avoid them by checking that $nums[i]$ = $nums[i + 1]$ while being sure that i doesn't go out of bounds.
		2. call backtrack

## References

[Neetcode](https://neetcode.io/solutions/subsets-ii)