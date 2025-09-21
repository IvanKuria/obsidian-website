
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
1. For each element in the matrix, iff it's equal to 1, we'll increment num_islands and call dfs(i, j). But what's dfs here?
2. **Base case**: if the indices are out of bounds(less than 0, >= to m or n) and if the current element is not 1
3. We'll then set the current element to 0 to indicate that the element has been seen
4. Then call dfs for the right(j + 1), up(i + 1), left(j - 1) and down(r - 1)
5. At the end, return num_islands
## References

[Greg Hogg](https://www.youtube.com/watch?v=gCswsDauXPc)