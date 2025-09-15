
2024-09-30  17:56

Status: #child 

Tags: [[Leetcode]] #leetcode #computer-science 

# Linked Lists
- they're a data structure in computer science similar to arrays.

## Singly Linked Lists
### Code Snippet

```python
# Singly Linked List

class SinglyNode:
	def __init__(self, val, next=None):
		self.val = val
		self.next = next
	
	def __str__(self):
		return str(self.val)
	
# Initialize the nodes
Head = SinglyNode(1)
A = SinglyNode(3)
B = SinglyNode(4)
C = SinglyNode(7)

# Connect the nodes
Head.next = A
A.next = B
B.next = C

print(Head) => 1
```

### Traverse the Singly Linked List

```python
# Traverse the list - O(n)
curr = Head

while curr:
	print(curr)
	curr = curr.next

# Result
1
3
4
7
```

### Display the Singly Linked List

```python
# Display the Linked List
def display(head):
	curr = head
	elements = []
	while curr:
		elements.append(str(curr.val))
		curr = curr.next
	print(' -> '.join(elements))

# Result
1 -> 3 -> 4 -> 7
```


### Search a Linked List

```python
def search(head, val):
	curr = head
	while curr:
		if val == curr.val:
			return True
		curr = curr.next
	return False

# Results
search(Head, 7) => True
```

## References


