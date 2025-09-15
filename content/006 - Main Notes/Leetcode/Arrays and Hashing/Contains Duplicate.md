
2024-10-11  21:26

Status: #child 

Tags: [[Leetcode]] #arrays 

# [Contains Duplicate](https://leetcode.com/problems/contains-duplicate/)

```python
class Solution(object):
    def containsDuplicate(self, nums):
        """
        :type nums: List[int]
        :rtype: bool
        """

        seen = {}

        for num in nums:
            if num not in seen:
                seen[num] = 0
            else:
                return True
        return False
```

### Explanation
- The trick is to use a hash set(dictionary)
## References
[Neetcode](https://leetcode.com/problems/contains-duplicate/)

