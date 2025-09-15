
2024-10-13  20:40

Status: #child 

Tags: [[Leetcode]] #leetcode-medium #leetcode #hash-maps #arrays 

# [Top K Frequent Elements](https://leetcode.com/problems/top-k-frequent-elements/)

### Code

```python
class Solution(object):
    def topKFrequent(self, nums, k):
        """
        :type nums: List[int]
        :type k: int
        :rtype: List[int]
        """

        if len(nums) == 0:
            return [0]
    
        seen = {}

        for num in nums:
            if num not in seen:
                seen[num] = 1
            else:
                seen[num] += 1
        
        result_list = []
        for x in range(k):
            most_freq = max(seen.values())
            for key in seen:
                if seen[key] == most_freq:
                    result_list.append(key)
                    seen.pop(key)
                    break

        return result_list
```

### Explanation
1. Iterate through *nums* and create a dictionary containing the count of each unique integer
2. Iterate through the values of the dict and find the max count. Do this k times
3. Return the max values in each iteration

## References
[Neetcode](https://leetcode.com/problems/top-k-frequent-elements/description/)

