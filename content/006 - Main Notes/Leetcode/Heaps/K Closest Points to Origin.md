---
title: "K Closest Points to Origin"
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
**Topic:** [[Heaps Intro]] | [[Leetcode MOC]] | [[Complexity Cheat Sheet]]


# [K Closest Points to Origin](https://leetcode.com/problems/k-closest-points-to-origin/)

### My Code

```python
import heapq

class Solution(object):
    def kClosest(self, points, k):
        """
        :type points: List[List[int]]
        :type k: int
        :rtype: List[List[int]]
        """

        # iterate through points and calculate the distance
        # store the distance as k and the index of the point as v as a tuple
        # heappush this tuple into a min heap and pop the k most elements

        heap = []
        inter = []

        # calcualte distance
        for i, p in enumerate(points):
            x1 = p[0]
            y1 = p[1]
            distance = sqrt(x1**2 + y1**2)
            heapq.heappush(heap, (distance, (x1, y1)))
        
        return [heapq.heappop(heap)[1] for _ in range(k)]

        # Time: O(nlogn)
        # Space: O(n)
```

### Explanation

1. iterate through points and calculate the distance
2. store the distance and the point in the heap. The point is stored as a heap(priority queue with distance as the priority)
3. heappush this tuple into a min heap and pop the k most elements(points) and put into an array and return
4. pretty straightforward :) but there's a better solution

### Optimal Solution

```python
import heapq

class Solution(object):
    def kClosest(self, points, k):
        """
        :type points: List[List[int]]
        :type k: int
        :rtype: List[List[int]]
        """

        # iterate through points and calculate the distance
        # store the distance as k and the index of the point as v as a tuple
        # heappush this tuple into a max heap and pop the k most elements

        def dist(x, y):
            return x**2 + y**2

        heap = []
        # calcualte distance
        for x, y in points:
            d = dist(x, y)
            if len(heap) < k:
                heapq.heappush(heap, (-d, x, y))
            else:
                heapq.heappushpop(heap, (-d, x, y))
        
        return [(x, y) for d, x, y in heap]

        # Time: O(logn)
        # Space: O(n)
```

### Explanation

1. This is better because k will almost always be significantly less than n.
2. Instead of adding all the points to the heap, we only keep track of the k smallest elements and pop the largest from the heap if the length is greater than k
## References

[Greg Hogg](https://www.youtube.com/watch?v=IGRUukbD6p8)
