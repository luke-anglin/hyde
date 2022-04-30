---
layout: post
title: Unit D - Study Guide
categories: algorithms
link:
---

# Flow Networks

1. What is an augmenting path?

- **Augmenting paths** contains only
  - Non-full forward edges
  - Non-empty backward edges

2. What are the residual graph $G_f$ edge equations?

- Forward: $c(e) - f(e)$
- Backward: $f(e)$

3. Explain the Ford-Fulkerson algo

- Initialize $f(e) = 0$ for all $e \in E$
- Construct residual network $G_f$, each forward edge set to $c(e)$, and no backward edges (meaning, there is 0 flow you could remove, because we have sent none)
- Continually increase flow by one unit along augmenting path, setting backward edges to $f(e)$ and forward to $c(e) - f(e)$

4. How many iterations?

- Integers - bounded by max flow ($|f^*|$),
- Rational values - integer capacity, $\approx 2^{32}$
- Irrational values could lead to an infinite loop

5. Running time?

- For integer capacities, $O(|f^*| * |E|)$, where $E$ comes from BFS and $|f^*|$ b/c bounded by max flow.

6. Edmond-karp runtime?

- $\Theta(\text{min}(|f^*| * |E|, |V||E^2|))$ = O(|V||E|^2)
- Note there are other algos that can do in diff way but total cubic, like $V^3$ or $V^2 E$

7. How did we prove MaxFlow/Ford-Fulkerson?

- Cut theorem
- Conservation of flow across cut from source to sink requires that $max|f| \le min\_cut$

# Maximum bipartite matching (dog lovers and dogs)

8. How do we reduce MBM to MF?

1. Make $G$ into $G'$, all edges will now have weight one
1. Call max flow on $G'$
1. Return $M$ as all 'middle edges' with flow 1

1. Runtime of MBM?

- $\Theta(E*V)$, because Karp does $min$, and $|f| \le L$

# Reductions

10. What are the three parts of a reduction?

- `convert(A->B)`
- `execute(B)` - we want this to be the slow part
- `solve(B->A)`

## Lower bound proofs

11. Explain lower bounds for reductions.

We know that if $A \in \Omega(f(n))$ then $B \in \Omega(f(n))$, so $A \le_p B$.

# MIS, MVC

12. Give the definition of MIS and how it can be converted to a decision problem.

- $S \subseteq V$ is an independent set if no two nodes in $S$ share an edge
- Convert to decision by saying 'Can I have a $k$ sized independent set?' - NP-Complete b/c polynomial verifiable

13. How do we convert from MIS to MVC?

- The complement of the independent $S$ is a vertex cover

# P, NP, NP-C, NP-H

14. What is an NP problem?

- Verifiable in polynomial time

15. What is an NP-Hard problem?

- Every problem in NP/P can reduce to it

16. What is an NP-Complete problem

- Satisfies verifiability of NP and an NP-Hard/NP-Complete problem reduces to it

17. How do we prove P = NP?

- If any NP-H or NP-C problem reduces to a problem in P (can be solved in polynomial time), then P = NP

# 3-SAT

18. What is 3-SAT?

- $OR$s in parentheses, $AND$s connect.
- Is there an assignment of $T$ or $F$ to each variable to make the 3-CNF true?
- NP-Hard

19. How does 3-SAT reduce to $k$IS?

- Triangle graphs of the CNFs, connect each variable to its complement
- Is there a $k$ independent set where $k =$ the number of triangles?
