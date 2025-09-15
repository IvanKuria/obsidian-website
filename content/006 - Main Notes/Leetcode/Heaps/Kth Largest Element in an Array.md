
2025-09-10  12:09

Status: #child 

Tags: #leetcode #leetcode-medium [[Leetcode]] #heaps [[Heaps Intro]]

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

## References

[Greg Hogg](https://www.youtube.com/watch?v=ZmGk7h8KZLs)
