
2025-09-16  09:29

Status: #adult

Tags: #leetcode #leetcode-easy [[Backtracking Intro]]

# [Kth Largest Element in a Stream](https://leetcode.com/problems/kth-largest-element-in-a-stream/)

### Code

```python
import heapq

class KthLargest(object):

    def __init__(self, k, nums):
        """
        :type k: int
        :type nums: List[int]
        """
        self.minHeap, self.k = nums, k
        heapq.heapify(self.minHeap)
        while len(self.minHeap) > self.k:
            heapq.heappop(self.minHeap)
        
        

    def add(self, val):
        """
        :type val: int
        :rtype: int
        """
        self.val = val
        heapq.heappush(self.minHeap, self.val)
        if len(self.minHeap) > self.k:
            heapq.heappop(self.minHeap)

        return self.minHeap[0]
```

### Explanation
1. We want to keep a min heap of size k since we only want the kth largest and most importantly, we aren't subtracting any values so it's fine to pop
2. **__init__**: we initialize our values and create the min heap. If the length of the min heap is greater than k, we just keep popping until it's not
3. **add**: we push val onto the heap however, if the heap's length is less than k, we pop. Then we return the first element of min heap.
## References

[Neetcode](https://neetcode.io/solutions/kth-largest-element-in-a-stream