
2024-10-14  21:20

Status: #child 

Tags: [[Leetcode]] #trees #binary-trees

# Binary Trees and Binary Search Trees

## Binary Search Setup

```python
# binary trees
class TreeNode:
	def __init__(self, val, left=None, right=None):
		self.val = val
		self.left = left
		self.right = right

	def __str__(self):
		return str(self.val)

# initalization
A = TreeNode(1)
B = TreeNode(2)
C = TreeNode(3)
D = TreeNode(4)
E = TreeNode(5)
F = TreeNode(10)

A.left = B
A.right = C
B.left = D
B.right = E
C.left = F

print(A) => 1
```

## Pre Order Recursive Traversal (DFS)

```python
def pre_order(node):
	# if node is null
	if not node:
		return 

	print(node)
	pre_order(node.left)
	pre_order(node.right)

pre_order(A) = 1, 2, 3, 4, 5, 10
```

## In Order Recursive Traversal (DFS)

```python
def in_order(node):
	# if node is null
	if not node:
		return 

	pre_order(node.left)
	print(node)
	pre_order(node.right)

pre_order(A) = 4, 2, 5, 1, 10, 3
```

## Post Order Recursive Traversal (DFS)


```python
def in_order(node):
	# if node is null
	if not node:
		return 

	pre_order(node.right)
	pre_order(node.left)
	print(node)

pre_order(A) = 4, 2, 5, 1, 10, 3
```

## References
[Greg Hogg](https://www.youtube.com/watch?v=EPwWrs8OtfI)

