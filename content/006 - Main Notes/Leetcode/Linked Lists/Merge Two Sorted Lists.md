
2025-09-23  19:04

Status: #adult

Tags: #leetcode #leetcode-easy #linked-lists #computer-science [[Leetcode]]

# [Merge Two Sorted Lists](https://leetcode.com/problems/merge-two-sorted-lists/)

### Code

```python
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution(object):
    def mergeTwoLists(self, list1, list2):
        """
        :type list1: Optional[ListNode]
        :type list2: Optional[ListNode]
        :rtype: Optional[ListNode]
        """
        
        head = ListNode(None)
        curr = head

        while list1 or list2:
            if list1 is None:
                curr.next = list2
                return head.next

            if list2 is None:
                curr.next = list1
                return head.next

            if list1.val < list2.val:
                curr.next = list1
                list1 = list1.next
            
            else:
                curr.next = list2
                list2 = list2.next
            curr = curr.next
        return head.next
```

### Explanation
1. We initialize a new linked list called head and set a var called curr to head. We'll use curr to build up the list and then use head to return
2. While list1 and list2, 
	1. If list1 is none(we reached the end), set curr.next = list2 and return head.next. Vice versa if list2 is None.
	2. If list1.val < list2.val, curr.next = list and we set list1 = list1.next. Vice versa if list2.val < list1.val
	3. Set curr = curr.next
3. return head.next
## References

[Deepti Talesra](https://www.youtube.com/watch?v=RkQ4t9t_c74) - goated