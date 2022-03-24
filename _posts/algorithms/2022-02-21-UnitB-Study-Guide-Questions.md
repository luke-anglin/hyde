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

6. Explain the BFS algorithm and what it's good for.

- Shortest path algo for **unweighted** graphs
- **Basically** - treat it as a tree, pulling apart the graph, similar to breadth first on binary tree

7. Explain the color meanings for BFS

- **White** - haven't seen vertex yet
- **Gray** - vertex is in the queue
- **Black** - vertex has been fully processed (removed from queue, neighbors seen and added)

8. What is its runtime and space complexity?

- $\Theta(V + E)$ for time, $\Theta(V)$ for space (coloring and queue)

9. Explain the recursive, not the stack, approach to DFS

- Initialize with `dfs_sweep(graph, start)` function, and then call `dfs_visit(graph, start, visited)` where `visited` is an array
- Keep calling on current node, which calls `dfs_visit()` on the adjacent neighbors, so you go deep first and then it bubbles up

10. Tell me about non-tree edges in a digraph.

- **Back edge** - from the lowest child vertex to a > parent ancestor
- **Descendant edge** - the opposite direction of a back edge, from the some > parent ancestor to a child vertex
- **Cross edge** - any other edge you can draw that isn't actually there, or a back edge, or a descendant edge

11. How do you recognize a cycle in a digraph and undigraph with DFS?

- To recognize one in a digraph, `dfs_visit()` sees a gray vertex that is already on the path from start node to this node - indicates a **back edge**
- To recognize in a undigraph, same thing, but you have to put a condition for parent nodes, since those shouldn't count.

12. How do you find a path to a specific vertex $v$ from a start node $s$ using DFS?

- Normal approach, just pop the $v$ off stack immediately when you hit it and stop after backtracking finishes (just end early, basically)

## Topo Sort

13.. Explain the topo sort algo

- Run `dfs_sweep(G)`, computing finish times along the way, and then arrange in descending order

14. If you tranpose $G$ and then topo sort, what is the result?

- A dependency graph

## SCCs

15. What is an SCC

- It's where there is a directed cycle and any vertex in the SCC can reach any other vertex in the SCC (**only for digraphs**)

16. Give the SCC finding algo

1. `DFS-Sweep(G)` - sweep for finish times
1. `G^T` - transpose
1. `DFS-Sweep(G^T)` - sweep the transpose for finish times, visiting in descending order, transpose prevents us from leaving SCCs and going in descending prevents us from 'redoing' SCCs

## MSTs

17. Give the two properties of an MST

- Contains all nodes in G
- Acyclic

18. Do Prim's and/or Kruskal's work for digraphs?

- No

19. Explain Kruskal's and give its runtime (with and w/out optimizations)

```python
while not spanning:
    try:
        spanning_tree.append(smallest_edge)
    except CreatesCycle:
        pass
```

- Without optimizations - $\Theta(V^3)$
- With optimizations - $\Theta(E \log V)$

20. Explain union by rank

```python
# Attach smaller rank tree under root of high rank tree
if x.rank > y.rank:
  y.p = x
else if x.rank < y.rank:
  x.p = y
else:
  # If ranks are equal, make one root and increment rank by one
  y.p = x
  x.rank += 1
```

21. Explain path compression

- Make direct connections on previous `find` operations (dynamic programming)

22. What is the heap used for in Kruskal's?

- Stores the edges, we can remove min edge on each iteration

## Prim's

15. Explain the purpose and structure of an indirect heap

**Purpose** - Logarithmic time `PQ.decreaseKey()`. The bubbling in the heap array after the change is the reason for logarithmic time. This results in going from $O(E*V)$ to $O(E \log V)$

Two arrays.

The `heap` array:

- Indices represent heap position, values represent vertex weights.

The `indirection` array:

- Indices represent vertex numbers (`v1`), values represent heap position.

16. What is the difference between Prims and Djikstra's

- Prim's only looks at adjacent $E$ weights, where Djikstra's looks at distances from root
