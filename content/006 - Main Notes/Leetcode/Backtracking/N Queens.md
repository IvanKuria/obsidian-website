---
title: "N Queens"
type: problem
difficulty: hard
techniques:
  - backtrack
date: 2025-09-16
maturity: growing
tags:
  - leetcode
  - cs
  - problem
---

# [N-Queens](https://leetcode.com/problems/n-queens/)

### Code

```python
class Solution(object):
    def solveNQueens(self, n):
        """
        :type n: int
        :rtype: List[List[str]]
        """
        
        col = set()
        posDiag = set()
        negDiag = set()

        res = []
        board = [["."] * n for _ in range(n)]

        def backtrack(r):
            # base case
            if r == n:
                copy = ["".join(row) for row in board]
                res.append(copy)
                return
            

            for c in range(n):

                # not a valid queen position
                if c in col or (r + c) in posDiag or (r - c) in negDiag:
                    continue

                col.add(c)
                posDiag.add(r + c)
                negDiag.add(r - c)
                board[r][c] = "Q"

                backtrack(r + 1)

                col.remove(c)
                posDiag.remove(r + c)
                negDiag.remove(r - c)
                board[r][c] = "."
        
        backtrack(0)
        return res
```

### Explanation

## References

[Neetcode](https://neetcode.io/solutions/n-queens)
