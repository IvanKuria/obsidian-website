

2025-09-09  20:47

Status: #child

Tags: #leetcode #leetcode-easy #heaps [[Heaps Intro]] [[Leetcode]]

# [Last Stone Weight](https://leetcode.com/problems/last-stone-weight/)

### Code

```python
import heapq

class Solution(object):
    def lastStoneWeight(self, stones):
        """
        :type stones: List[int]
        :rtype: int
        """

        # implement a max heap
        n = len(stones)

        for i in range(n):
            stones[i] = -stones[i]

        heapq.heapify(stones)
        
        while len(stones) > 1:
            y = heapq.heappop(stones)
            x = heapq.heappop(stones)
            if y != x:
                y -= x
                heapq.heappush(stones, y)
        if len(stones) == 1:
            return -heapq.heappop(stones)
        return 0
```

### Explanation
1. This involves a max heap
2. Essentially we'll keep popping the largest 2 elements and do the comparisons.
	1. We'll push the difference if the elements are unique
3. Return the largest element if available, else 0

## References

[Greg Hogg](https://www.youtube.com/watch?v=a2dEXlmA1nc)
