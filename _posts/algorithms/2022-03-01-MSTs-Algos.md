---
layout: post
title: MST Algorithms
categories: algorithms
link: https://uva-cs.github.io/cs4102-s22/slides/cs4102_L11-kruskal-find-union.pdf
---

## MSTs

- A **spanning tree** is a **tree** that is a subset of $G$
  - Contains all nodes in $G$
  - Acyclic
  - Construct-able by arbitrarily removing edges
- An **MST** uses the least amount of edges

## Kruskal's

For **undirected graphs**

```python
while not spanning:
    try:
        spanning_tree.append(smallest_edge)
    except CreatesCycle:
        pass
```

### Disjoint set code

![Disjoint Set Code](https://i.imgur.com/W05SQZP.png)

**General idea**:

- If the two vertices connected by the chosen edge are in disjoint sets, then we can add it to the spanning tree and update the sets.

### Runtime

#### Before Path Comopression

- Every edge placed on heap once and removed once
  - $\Theta(E \log E) = \Theta(E \log V)$
- Overall time is $O(V^3)$
  - $\Theta(E (2 f(V) + u(V)))$

#### After Path Compression

- $\Theta(E \log V)$

# Union/Find and Disjoint Sets

An **ADT** is a collection where an item can only belong to one specific set

## Necessary Operations

- `void makeSet(int n)` - initialize $n$ independent sets
  - store as an array of $n$ size, where each location stores a label
  - every index maps to the label in the tree. The value of the index is the parent of that node, except for the `root` which stores itself.
- `int findSet(int i)` - which set does $i$ fall into?
  - trace to `root`

```python
def findSet(i):
    a = [blah, blah, blah] # some array
    initial_idx = i
    while True: # Max iterations is n
        if a[i] == i:
            return i
        else:
            i = a[i] # Follow the link
```

- `void union(int i, int j)` - merge sets containing $i$ and $j$
  - make one `root_i` a child of the other `root_j`

```python
def union(i, j):
    label1 = find(i)
    label2 = find(j)
    a[label1] = label2 # or vice versa
```

## Representing Sets as Trees

- Identify a set by its **root node ID**

## Optimizations

### Union by Rank

- Create a second member to each array, `rank`

```python
if x.rank > y.rank:
    y.p = x
else:
    x.p = y
```

### Path Compression

- Make direct connections on previous `find` operations (dynamic programming)
