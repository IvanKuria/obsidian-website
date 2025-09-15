
2024-10-05  20:20

Status: #child 

Tags: [[Leetcode]]

#  [Reverse Linked List](https://leetcode.com/problems/reverse-linked-list/)

### Code
```python
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next

class Solution(object):
    def reverseList(self, head):
        """
        :type head: ListNode
        :rtype: ListNode
        """
        prev, curr = None, head
        while curr:
            nxt = curr.next
            curr.next = prev
            prev = curr
            curr = nxt
        return prev
```

### Explanation
1. We initialize two pointers, one that points to the current node(*curr*) and one that points to the previous node(*prev*)
2. We initialize a while loop that checks if the current node(*curr*) is Null.
3. Set a var *nxt* = *curr.next*(next node) in order to store it for later(you'll see why)
4. Set curr.next = to the previous node(prev)
5. Set the prev = curr
6. Set curr = nxt

### Big O
## References
[Neetcode](https://leetcode.com/problems/reverse-linked-list/)
