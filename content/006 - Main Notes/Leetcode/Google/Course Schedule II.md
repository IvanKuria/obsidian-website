---
title: "Course Schedule II"
type: problem
difficulty: medium
techniques:
  - graphs
date: 2025-09-18
maturity: evergreen
tags:
  - leetcode
  - cs
  - problem
---

# [Course Schedule II](https://leetcode.com/problems/course-schedule-ii/)

### Code

```python
from collections import defaultdict

class Solution(object):
    def findOrder(self, numCourses, prerequisites):
        """
        :type numCourses: int
        :type prerequisites: List[List[int]]
        :rtype: List[int]
        """

        # edge case: no prereqs
        if not prerequisites:
            return [i for i in range(numCourses)]

        d = defaultdict(list)
        courses = prerequisites
        res = []
        for a, b in courses:
            d[a].append(b)

        UNVISITED = 0
        VISITING = 1
        VISITED = 2
        states = [UNVISITED] * numCourses

        def dfs(node):
            state = states[node]
            if state == 2:
                return True
            elif state == 1:
                return False

            states[node] = VISITING
            for nei_node in d[node]:
                if not dfs(nei_node):
                    return False
            
            states[node] = VISITED
            res.append(node)
            return True

        for i in range(numCourses):
            if not dfs(i):
                return []

        return res
```

### Explanation
1. It's just like [[Course Schedule]], except we have to keep track of each visited element as they are visited. This is done by simply appending them to a result list
## References

Me :)
