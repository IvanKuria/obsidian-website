---
title: "Kth Largest Element in an Array"
type: problem
difficulty: medium
techniques:
  - heaps
date: 2025-09-10
maturity: growing
tags:
  - leetcode
  - cs
  - problem
---

# [Kth Largest Element in an Array](https://leetcode.com/problems/kth-largest-element-in-an-array/)

### Code

```python
import heapq

class Solution(object):
    def findKthLargest(self, nums, k):
        """
        :type nums: List[int]
        :type k: int
        :rtype: int
        """
        
        # max heap
        heap = []
        for num in nums:
            if len(heap) < k:
                heapq.heappush(heap, num)
            else:
                heapq.heappushpop(heap, num)
        return heap[0]
```

### Explanation
1. Just like [[K Closest Points to Origin]] without the distance calculations
2. Iterate through nums, and if the heap length is less than k, well push
3. Else: heappushpop the current num
4. Return the first element in heap(heap[0])
## References

[Greg Hogg](https://www.youtube.com/watch?v=ZmGk7h8KZLs)
