
2025-09-17  12:08

Status: #child

Tags: #leetcode #leetcode-medium #graphs #computer-science [[Leetcode]] [[Graphs Intro]]

# [Number of Islands](https://leetcode.com/problems/number-of-islands/)

### Code

```python
class Solution(object):
    def numIslands(self, grid):
        """
        :type grid: List[List[str]]
        :rtype: int
        """
        m, n = len(grid), len(grid[0])
        num_islands = 0

        def dfs(i, j):
	        # base case
            if i < 0 or i >= m or j < 0 or j >= n or grid[i][j] != "1":
                return

            grid[i][j] = "0"
            dfs(i, j + 1) # right
            dfs(i + 1, j) # up
            dfs(i, j - 1) # left
            dfs(i - 1, j) # down


        
        for i in range(m):
            for j in range(n):
                if grid[i][j] == "1":
                    num_islands += 1
                    dfs(i, j)

        return num_islands
```

**Time and Space**: $O(m * n)$
### Explanation
1. 
## References

[Greg Hogg](https://www.youtube.com/watch?v=gCswsDauXPc)