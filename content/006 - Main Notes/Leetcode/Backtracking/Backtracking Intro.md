
2025-09-15  17:27

Status: #adult 

Tags: #computer-science #leetcode #backtrack 

# Backtracking

## Template

### 1. Base Case
### 2. Choices
### Constraints
### Backtracking Step

#### Example

1. Given two integers $n$ and $k$, return all possible combinations of $k$ numbers chosen from the range of $[1, n]$. You may return the answer in any order.
##### Code

```python
class Solution(object):
    def combine(self, n, k):
        """
        :type n: int
        :type k: int
        :rtype: List[List[int]]
        """
        
        res, sol = [], []
        nums = [x for x in range(1, n + 1)]
        
        def backtrack(i):
            # base case
            if len(sol) == k:
                res.append(sol[:])
                return

            if i == n:
                return
            
            # go left
            sol.append(nums[i])
            backtrack(i + 1)
            sol.pop()

            # go right
            backtrack(i + 1)

        backtrack(0)
        return res
```

##### Explanation
**Base Case(s)**: 
	- When the len(sol) == k
	- When the index(i) == n(length of array)

**Choices**:
	- All numbers from current index to n
	- *Going left*: this means that we deciding to add a number(add the num to sol, backtrack on i + 1 then sol.pop)
	- *Going right*: this means we are choosing not to add a number(increment i)

**Constraints**: the length of sol must be exactly k

**Backtracking Step**: Pop the last number added
## References

[Bitflip](https://www.youtube.com/watch?v=p9m2LHBW81M) however my solution resembles something Greg Hogg would do.