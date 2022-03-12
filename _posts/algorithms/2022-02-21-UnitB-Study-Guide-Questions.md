---
layout: post
title: Unit B Study Guide Questions
categories: algorithms
---

# Graphs

## Terminology

1. When is a path simple?

- When you don't go over the same vertex again

2. What is a connected graph?

- For each pair of vertices, I can find some path to get from $v_1$ to $v_2$. This applies to **undirected graphs**

3. What is a strongly connected digraph?

- The same as connected, but with digraphs (bidirectional connections)

3. What do you call a graph where every node connects to every other?

- A complete graph

4. How many edges can you have in a maximally dense graph, both for undirected and directed?

- $E = V(V - 1) / 2$ and $E = V(V-1)$ respectively

5. What do we call a connected, acyclic undirected graph? What about if just acyclic?

- A free tree. A forest.

## BFS and DFS

6. Explain the BFS algorithm and what it's good for

- Good for SP algorithm for **unweighted** graphs
- Basically treat it as a tree, pulling apart the graph, similar to breadth first on binary tree

7. What is its runtime and space complexity?

- $\Theta(V + E)$ for time, $\Theta(V)$ for space (coloring and queue)

8. How does the DFS algorithm differ from BFS

- Uses the same algorithm with a stack rather than a queue

## Topo Sort

9. Explain the topo sort algo

- Run `dfs_sweep(G)`, computing finish times along the way, and then arrange in descending order

10. If you tranpose $G$ and then topo sort, what is the result?

- A dependency graph

## SCCs

11. What is an SCC

- It's where there is a directed cycle and any vertex in the SCC can reach any other vertex in the SCC (**only for digraphs**)

## MSTs

12. Give the two properties of an MST

- Contains all nodes in G
- Acyclic

13. Do Prim's and/or Kruskal's work for digraphs?

- No

### Union by Rank

14. If `x.rank == y.rank`, what do you do?

- Make one the parent of the other, let's say `y.p = x` (set x to be the parent of y) and increment the rank of x.

## Prim's

15. Explain the purpose and structure of an indirect heap

**Purpose** - Logarithmic time `PQ.decreaseKey()`. The bubbling in the heap array after the change is the reason for logarithmic time.

Two arrays.

The `heap` array:

- Indices represent heap position, values represent vertex weights.

The `indirection` array:

- Indices represent vertex numbers (`v1`), values represent heap position.

16. What are the three differences between Prim's and Djikstra's?

1. Only Prim's works for negative weights
1. Prim's only works for undirected graphs
1. Different goals, MST vs shortest path algo
