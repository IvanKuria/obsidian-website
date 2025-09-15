
2024-12-20  17:22

Status: #child #leetcode #leetcode-easy 

Tags: #arrays #sets [[Leetcode]]

# Missing Number

### Code
```python
class Solution(object):
    def missingNumber(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """

        ideal = [x for x in range(len(nums) + 1)]
        return list(set(ideal) - set(nums))[0]
```

### Explanation
- first create the list containing all the numbers from $0$ to $n$. 
- By using sets we can find the difference between them by subtracting the set of the ideal list from the set of nums. { $set(ideal) - set(nums)$ }


## References

