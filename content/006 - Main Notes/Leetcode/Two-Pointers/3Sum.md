
2024-08-22  12:49

Status: #baby 

Tags: [[Leetcode]] [[Two Sum II - Input Array Is Sorted]] #two-pointers #leetcode 

# 3Sum

### Code
```python
class Solution(object):

	def threeSum(self, nums):
	"""
	:type nums: List[int]
	:rtype: List[List[int]]
	"""
	
		res = []
		
		# sorts nums in ascending order
		nums.sort()
		
		for i, num in enumerate(nums):
			if num > 0:
				break
		
			# checks if the current element isn't the first element
			# and if the current element isn't equal to the prev element
			# because we can't use duplicates
			if i > 0 and num == nums[i - 1]:
			
				# go the next iteration of the loop
				continue
				
			# two sum implementation
			l, r = 0, len(nums) - 1
			threeSum = num + nums[l] + nums[r]
			while l < r:
				if threeSum > 0:
					r -= 1
				elif threeSum < 0:
					l += 1
				else:
					res.append([num, nums[l], nums[r]])
					# update the pointers
					l += 1
					r -= 1
					while nums[l] == nums[l - 1] and l < r:
						l += 1
		return res
```




## References
[Neetcode](https://www.youtube.com/watch?v=jzZsG8n2R9A&t=741s)


