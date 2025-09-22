
2025-09-22  00:21

Status: #adult

Tags: #leetcode #leetcode-easy #tries #google #strings #arrays [[Leetcode]]

# [Longest Common Prefix](https://leetcode.com/problems/longest-common-prefix/)

### Code

```python
class Solution(object):
    def longestCommonPrefix(self, strs):
        """
        :type strs: List[str]
        :rtype: str
        """
        
        # edge case where strs is empty
        if not strs:
            return ""

        min_len = min(len(s) for s in strs)
    
        for i in range(min_len):
            char = strs[0][i]
            for s in strs:
                if s[i] != char:
                    return strs[0][:i]

        return strs[0][:min_len]
```

### Explanation
1. We first account for the edge case where the array is empty
2. Since we'll be using an index, we have to determine its upper bound by using the len of the shortest word in the array
3. Then we just check each character in each word of the array to each character in the first word and if we determine that there's no match, we just return the the characters of the first word up until i(index)
**Note**: I thought of this solution during my initial approach but saw a time complexity of O(m * n) and thought it could be better.
## References

[Greg Hogg](https://www.youtube.com/watch?v=8C6F8_nM0qs)