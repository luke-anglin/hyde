---
layout: post
categories: algorithms
title: Graphs
link:
---

## Terminology

- Undirected: $E = V(V - 1) / 2$ - a _complete graph_, each vertex reachable from all others
- Directed $E = V(V-1)$ - indegree and outdegree concept
- A path is **simple** if it contains an edge at most once
- **Strongly connected digraph** - node $u$ may be reachable from $v$ but not necessarily vice versa
- A connected, acyclic undirected graph is called a **free tree**
  - If we specify a root, it's a **rooted tree**
  - Acyclic but not connected is an undirected **forest**
- Directed, acyclic graphs are called **DAGs**

## Data structures for Undirected Graphs

- Adjacency matrix: $A[u][v] = 1$ `if edge(u,v) exists`
- Adjacency list: Each edge $(u,v)$ node has a list of the nodes it connects to

### For weighted graphs

- Store weight in matrix cell
- Add field to node object

# Traversal

## BFS Shortest Path

- Choose a starting vertex
- Visit in order of increasing distance
- Good for **undirected graphs**

### Pseudocode

![](https://i.imgur.com/fpAI7Ew.png)

### Running time

- Time - $\Theta(n)$
- Space - $\Theta(V)$

## DFS

Same process as BFS but uses a stack

- Go as deep as possible
- Backtrack as little as possible until you can find another path down
