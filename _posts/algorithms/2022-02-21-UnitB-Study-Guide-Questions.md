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

## Algorithms

### BFS and DFS

6. Explain the BFS algorithm and what it's good for

- Good for SP algorithm for **unweighted** graphs
- Basically treat it as a tree, pulling apart the graph, similar to breadth first on binary tree

7. What is its runtime and space complexity?

- $\Theta(V + E)$ for time, $\Theta(V)$ for space (coloring and queue)

8. How does the DFS algorithm differ from BFS

- Uses the same algorithm with a stack rather than a queue
