
2024-10-13  20:33

Status: #child

Tags: [[Leetcode]] #leetcode-medium #leetcode #hash-maps

# [Group Anagrams](https://leetcode.com/problems/group-anagrams/)

### Code 

```python
class Solution(object):
    def groupAnagrams(self, strs):

        """
        :type strs: List[str]
        :rtype: List[List[str]]
        """
        
        seen = {}

        for word in strs:
            sorted_word = "".join(sorted(word))
            if sorted_word not in seen:
                seen[sorted_word] = [word]
            else:
                seen[sorted_word].append(word)

        return seen.values()
```

### Explanation
1. Pretty self explanatory

## References

[Neetcode](https://leetcode.com/problems/group-anagrams/description/)