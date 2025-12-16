
2025-09-21  09:55

Status:

Tags: #leetcode #leetcode-medium #dynamic-programming #google #two-pointers [[Leetcode]]

# [Best Time to Buy and Sell Stock II](https://leetcode.com/problems/best-time-to-buy-and-sell-stock-ii/)

### Code

```python
class Solution(object):
    def maxProfit(self, prices):
        """
        :type prices: List[int]
        :rtype: int
        """
        
        n = len(prices)
        lo, hi = prices[0], prices[0]
        i = 0
        profit = 0

        while i < n - 1:
            # where to buy
            while i < n - 1 and prices[i] >= prices[i + 1]:
                i += 1
            lo = prices[i]

            # where to sell
            while i < n - 1 and prices[i] <= prices[i + 1]:
                i += 1
            hi = prices[i]
            profit += hi - lo

        return profit
```

### Explanation
1. We'll keep track of the places to buy(lo) and places to sell(hi)
2. When prices[i] >= prices[i + 1], this is where we buy, we increment i and set lo = prices[i]
3. When prices[i] <= prices[i + 1], this is where we sell, we increment i and set hi = prices[i] and calculate profit
## References

[Greg Hogg](https://www.youtube.com/watch?v=TSpBHe5vInA)