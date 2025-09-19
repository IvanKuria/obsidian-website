
2025-09-18  11:03

Status: #adult

Tags: #leetcode #leetcode-medium #heaps [[Leetcode]] [[Heaps Intro]]

# [Top K Frequent Words](https://leetcode.com/problems/top-k-frequent-words/)

### Code

```python
from collections import Counter

class Solution(object):
    def topKFrequent(self, words, k):
        """
        :type words: List[str]
        :type k: int
        :rtype: List[str]
        """

        # implement a max heap(k: freq, v: word)
        res = []

        count = Counter(words)
        maxHeap = [(-v, n) for n, v in count.items()] # we only want the frequencies
        heapq.heapify(maxHeap)

        for i in range(k):
            word = heapq.heappop(maxHeap)[1]
            res.append(word)

        return res
```

### Explanation
1. Basically store the freq and word in a max heap and return the k frequent words
## References

Me