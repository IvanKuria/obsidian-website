
2025-09-11  17:32

Status: #child

Tags: #leetcode #leetcode-medium #backtrack [[Subsets]] #computer-science 

# [Combination Sum](https://leetcode.com/problems/combination-sum/)

### Code

```python
class Solution(object):
    def combinationSum(self, candidates, target):
        """
        :type candidates: List[int]
        :type target: int
        :rtype: List[List[int]]
        """
        res, sol = [], []
        n = len(candidates)

        def backtrack(i, cur_sum):
            # 1. index out of range and sum > target
            if i == n or cur_sum > target:
                return
                
			# 2. we actually get the target
            if cur_sum == target:
                res.append(sol[:])
                return

            backtrack(i + 1, cur_sum) # use the same value

            sol.append(candidates[i])
            backtrack(i, cur_sum + candidates[i])
            sol.pop()

        backtrack(0, 0)
        return res
```

### Explanation
1. It's similar to [[Subsets]] but we can use duplicates. We'll have a backtrack function that takes an index, i and and sum, cur_sum
2. **Base cases**:
	1. We achieve the target
		1. append to res and return
	2. Index is out of range or the current sum > target
		1. just return
3. **Left**: this path means we keep using the same num at i. so just increment i
4. **Right**: this is a little more involved. 
	1. We'll add the current num at i to sol
	2. We'll call backtrack on i and the current sum + the num at i. 
	3. sol.pop()
5. Call backtrack(0, 0) and return
6. Complexity:
	1. **Time**: $O(n ^ t)$
	2. **Space**: $O(n)$
## References

[Greg Hogg](https://www.youtube.com/watch?v=utBw5FbYswk) 