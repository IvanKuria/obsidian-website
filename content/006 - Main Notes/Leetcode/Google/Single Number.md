
2025-09-22  00:41

Status: #adult

Tags: #leetcode #leetcode-easy #google #strings #bit-manipulation [[Leetcode]]

# [Single Number](https://leetcode.com/problems/single-number/)

### Code

```python
class Solution(object):
    def singleNumber(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """

        # Constraints: 
            # Time: O(n)
                # everything is being done within the array
            # Space: O(1)
                # can use variables
        
        a = 0

        for num in nums:
            a ^= num

        return a
```

### Explanation
1. We'll be utilizing bitwise operator, XOR. It essentially determines if two numbers are different. If the numbers are different, it returns 1, else 0
2. At first look, it seems like it isn't too helpful since if we use [1, 2, 3, 2, 1] using XOR isn't too intuitive.
3. However, XOR uses the associative property; meaning that $$1 \oplus 2 \oplus 3 \oplus 2 \oplus 1$ = $1 \oplus 1 \oplus2 \oplus 2 \oplus 3 = 0 \oplus 0\oplus 3 = 0 \oplus 3 = 3$$
4. This is because we aren't actually using the base 10 representation of the numbers, but rather their binary representation
5. We'll set a = 0, iterate through nums and call xor on a and num
6. Return a
![[Pasted image 20250922004849.png | 400]]
## References

[Greg Hogg](https://leetcode.com/problems/single-number/submissions/1778842259/?envType=company&envId=google&favoriteSlug=google-thirty-days)