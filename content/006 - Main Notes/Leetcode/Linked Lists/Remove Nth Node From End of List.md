
2024-10-09  21:02

Status:  #adult

Tags: [[Leetcode]] #two-pointers #linked-lists 

# [Remove Nth Node From End of List](https://leetcode.com/problems/remove-nth-node-from-end-of-list/)

### Code

```python
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next

class Solution(object):
    def removeNthFromEnd(self, head, n):
        """
        :type head: ListNode
        :type n: int
        :rtype: ListNode
        """

        dummy = ListNode(0, head)
        left = dummy
        right = head

		# sets the right pointer n nodes away from the left pointer
        while n > 0 and right:
            right = right.next
            n -= 1

        while right:
            right = right.next
            left = left.next

		# delete the specified node
        left.next = left.next.next

        return dummy.next
```

### Explanation
1. we have to initialize a *dummy node* that way when we increment the left pointer, it will land on the intended node. The dummy node becomes the new "head"
2. The first while loop sets the right pointer
3. The second while loop increments the pointers until the right pointer reaches the tail
4. At this point the left pointer has landed on the intended node to delete. We set *left.next* = *left.next.next*
5. Return *dummy.next* not dummy because we want the original linked list
## References
[Neetcode](https://leetcode.com/problems/remove-nth-node-from-end-of-list/submissions/1417644681/)

