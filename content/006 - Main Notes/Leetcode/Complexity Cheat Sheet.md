---
title: Complexity Cheat Sheet
type: reference
tags:
  - leetcode
  - cs
  - algorithms
---

# Complexity Cheat Sheet

## Data Structure Operations

| Data Structure | Access | Search | Insert | Delete | Space |
|----------------|--------|--------|--------|--------|-------|
| Array | O(1) | O(n) | O(n) | O(n) | O(n) |
| Stack | O(n) | O(n) | O(1) | O(1) | O(n) |
| Queue | O(n) | O(n) | O(1) | O(1) | O(n) |
| Singly Linked List | O(n) | O(n) | O(1) | O(1) | O(n) |
| Doubly Linked List | O(n) | O(n) | O(1) | O(1) | O(n) |
| Hash Table | — | O(1) avg | O(1) avg | O(1) avg | O(n) |
| BST (balanced) | O(log n) | O(log n) | O(log n) | O(log n) | O(n) |
| Min/Max Heap | — | O(n) | O(log n) | O(log n) | O(n) |
| Trie | — | O(k) | O(k) | O(k) | O(n·k) |

> k = length of key/word, n = number of elements

## Sorting Algorithms

| Algorithm | Best | Average | Worst | Space | Stable? |
|-----------|------|---------|-------|-------|---------|
| Bubble Sort | O(n) | O(n²) | O(n²) | O(1) | Yes |
| Selection Sort | O(n²) | O(n²) | O(n²) | O(1) | No |
| Insertion Sort | O(n) | O(n²) | O(n²) | O(1) | Yes |
| Merge Sort | O(n log n) | O(n log n) | O(n log n) | O(n) | Yes |
| Quick Sort | O(n log n) | O(n log n) | O(n²) | O(log n) | No |
| Heap Sort | O(n log n) | O(n log n) | O(n log n) | O(1) | No |
| Counting Sort | O(n+k) | O(n+k) | O(n+k) | O(k) | Yes |
| Radix Sort | O(nk) | O(nk) | O(nk) | O(n+k) | Yes |

## Graph Algorithms

| Algorithm | Time | Space | Use Case |
|-----------|------|-------|----------|
| BFS | O(V+E) | O(V) | Shortest path (unweighted), level-order |
| DFS | O(V+E) | O(V) | Cycle detection, topological sort, connected components |
| Dijkstra's | O((V+E) log V) | O(V) | Shortest path (weighted, no negative) |
| Bellman-Ford | O(V·E) | O(V) | Shortest path (negative weights) |
| Topological Sort | O(V+E) | O(V) | Dependency ordering (DAGs) |
| Union-Find | O(α(n)) ≈ O(1) | O(n) | Connected components, cycle detection |

## Common Patterns — Time Complexity

| Pattern | Typical Complexity | Example |
|---------|-------------------|---------|
| Two Pointers | O(n) | [[3Sum]], [[Container with Most Water]] |
| Sliding Window | O(n) | [[Best Time to Buy and Sell Stock]] |
| Binary Search | O(log n) | [[Binary Search]], [[Koko Eating Bananas]] |
| Hash Map lookup | O(1) avg | [[Two Sum]], [[Group Anagrams]] |
| DFS/BFS on grid | O(m·n) | [[Number of Islands]], [[Max Area of Island]] |
| Backtracking | O(2ⁿ) or O(n!) | [[Subsets]], [[Permutations]], [[N Queens]] |
| Dynamic Programming | O(n²) or O(n·m) | [[Climbing Stairs]], [[House Robber]] |
| Heap operations | O(n log k) | [[Top K Frequent Elements]], [[Kth Largest Element in an Array]] |

## Quick Reference

- **O(1)** — hash lookups, array index, stack push/pop
- **O(log n)** — binary search, balanced BST ops
- **O(n)** — linear scan, two pointers, sliding window
- **O(n log n)** — efficient sorting (merge, quick, heap)
- **O(n²)** — nested loops, brute force pairs
- **O(2ⁿ)** — subsets, recursion without memoization
- **O(n!)** — permutations, brute force TSP

