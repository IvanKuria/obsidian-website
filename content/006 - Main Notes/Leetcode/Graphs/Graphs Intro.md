
2025-09-17  10:22

Status: #adult 

Tags: #leetcode #computer-science #graphs
# Graphs

![[Pasted image 20250917102354.png]]

### Array of Edges (Directed) [Start, End]

```python
n = 8 # number of nodes
A = [[0, 1], [1, 2], [0, 3], [3, 4], [3, 6], [3, 7], [4, 2], [4, 5], [5, 2]]
```

### Convert Array of Edges -> Adjacency Matrix

```python
M = []

# creates an n x n matrix
for i in range(n):
	M.append([0] * n)
	
for u, v in A:
	M[u][v] = 1
```

### Convert Array of Edges -> Adjacency List

```python
from collections import defaultdict

D = defaultdict(list)

for u, v in A:
	D[u].append(v)
```

![[Pasted image 20250917103012.png]]

### DFS with Recursion

```python
source = 0

seen = set() # keeps track of nodes we've already visited
seen.add(source) # we just add the source to get things started
def dfs(node):
	print(node)
	for nei_node in D[node]:
		if nei_node not in seen:
			seen.add(nei_node)
			dfs(nei_node)
		
dfs(source)
```

**Time and Space**: $O(V + E)$ where $V$ is the number of nodes and $E$ is the number of edges
### Iterative DFS with Stack

```python
source = 0

seen = set() # keeps track of nodes we've already visited
seen.add(source) # we just add the source to get things started
stack = [source]

while stack:
	node = stack.pop()
	# print(node)
	for nei_node in D[node]:
		if nei_node not in seen:
			seen.add(nei_node)
			stack.append(nei_node)
```

**Time and Space**: $O(V + E)$ where $V$ is the number of nodes and $E$ is the number of edges

### BFS with Queue

```python
from collections import deque

source = 0

seen = set()
seen.add(source)
q = dequeue()
q.append(source)

while q:
	node = q.popleft()
	print(node)
	for nei_node in D[node]:
		if nei_node not in seen:
			seen.add(nei_node)
			q.append(nei_node)
			 
```
## References

[Greg Hogg](https://www.youtube.com/watch?v=4jyESQDrpls&t=1737s)