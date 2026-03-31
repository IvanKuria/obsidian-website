---
title: "Task Scheduler"
type: problem
difficulty: medium
techniques:
  - heaps
date: 2025-09-11
maturity: growing
tags:
  - leetcode
  - cs
  - problem
---
**Topic:** [[Heaps Intro]] | [[Leetcode MOC]] | [[Complexity Cheat Sheet]]


#  [Task Scheduler](https://leetcode.com/problems/task-scheduler/)

### Code

```python
import heapq
from collections import Counter

class Solution(object):
    def leastInterval(self, tasks, n):
        """
        :type tasks: List[str]
        :type n: int
        :rtype: int
        """

        count = Counter(tasks)
        maxHeap = [-cnt for cnt in count.values()] # we only want the frequencies
        heapq.heapify(maxHeap)

        time = 0
        q = deque() # creates the queue
        while maxHeap or q:
            time += 1
            if maxHeap:
                cnt = 1 + heapq.heappop(maxHeap)
                if cnt: # not zero
                    q.append([cnt, time + n])
            if q and q[0][1] == time:
                heapq.heappush(maxHeap, q.popleft()[0])
        return time
```


### Explanation

1. We need to know the occurrences of each element in tasks in order to create a max heap.
2. We also need to keep track of how much `time` has passed between each task so we initialize time to 0.
3. As long as max heap and the queue aren't empty, we increment time.
	1. Then we add the new count(count + 1 because of max heap) and the time(time + n) to the queue to know when to push it back into the max heap for processing.
	2. if the queue isnt empty and the time for the task == current time, we can push the count back into the max heap
## References

[Neetcode](https://www.youtube.com/watch?v=s8p8ukTyA2I)
