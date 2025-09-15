
2024-09-09  22:25

Status: 

Tags: [[Leetcode]] #leetcode #leetcode-easy #two-pointers [[Two Sum]] 

# [Best Time to Buy and Sell Stock](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/)

### Code
```python
class Solution(object):

	def maxProfit(self, prices):
	
		"""		
		:type prices: List[int]		
		:rtype: int		
		"""		
		
		l, r = 0, 1		
		maxProfit = 0
		
		while r <= len(prices) - 1:		
			if prices[l] < prices[r]:			
				curProfit = prices[r] - prices[l]		
				maxProfit = max(curProfit, maxProfit)	
			else:
				l = r		
			r += 1		
		return maxProfit
```

### Explanation
1. Initialize a left(buy) and right pointer(sell)
2. We only change the right pointer if it's more than the left pointer. If that happens we increase the right pointer by 1 while checking a new max profit
3. If the above step fails, we set the left pointer to the right pointer because at that point the right pointer points to the new lowest price
4. Regardless of all the conditionals, we must increment the right pointer by 1
## References
[Neetcode](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/)

