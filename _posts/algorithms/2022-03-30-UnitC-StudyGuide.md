---
layout: post
title: Unit C Study Guide
categories: algorithms
---

# Dynamic Programming Slidesets

1. [Log-cutting](https://uva-cs.github.io/cs4102-s22/slides/cs4102-C-lecture1.pdf)
2. [Matrix Mult, LCS, Seam Carving](https://uva-cs.github.io/cs4102-s22/slides/cs4102-C-lecture2-3.pdf)
3. [Gerrymandering, Pseudo-polynomial time](https://uva-cs.github.io/cs4102-s22/slides/cs4102-C-lecture4.pdf)

# Dynamic Programming in General

1. What is an optimal substructure?

- A solution to a smaller optimal solution that helps solve a larger problem

2. What is the DP strategy

- Identify the recursive structure - **what is the last thing done**
- Save solutions in memory
- Choose top-down for recursive solutions and bottom-up for iterative (remember, b is closer to i)

3. Give the general algorithm for DP, at least summarize or close

For **top down**

- If in memory, return that
- If not, return subproblem
- If reach base case, put in memory after solving

For **bottom up**

- Initialize base cases
- Iterate on next subproblem using the base case solutions stored in memory
- Return `M[n]`

# Matmul

4. When multiplying two or more matrices, what is the shape of the output?

- The rows of the first one and the columns of the last one

5. How many operations does it take to multiply two matrices?

- The two unmatching parts (rows of the first, columns of the second) multiplied times the matching part (the rows of the second (or cols of first))

6. What function are we trying to minimize for `Best(i, j)` and what's the runtime?

- `Best(i, k) + Best(k+1, j)` + $r_ir_{k+1}c_j$ - $\Theta(n^3)$

7. What does `Choice[i, j]` represent in matmul?

- Best split for that cell was right after $M_k$

8. Explain the LCS cases:

![LCS](https://i.imgur.com/2ebKEOh.png)

9. LCS runtime?

$\Theta(n*m)$

10. Reconstructing LCS approach

- Start in bottom right of memory table
- If symbols match (green), go up-left diagonal
- Else, go to largest adjacent (up or left)

# Seam Carving

11. What's the approach and runtime?

- Build a pyramid from top to bottom, saving all pixel values in $M$
- $\Theta(2n)$ time to update pixels, $\Theta(n+m)$ (where $n$ and $m$ are the rows and columns) to find min and backtrack

# Gerrymandering

12. Explain how we gerrymander (assigning precincts $\{p_1, p_2 \dots \}$ to two districts $D_1, D_2$ with $n$ number of precincts and $m$ mad voters) and it's runtime

- $S(j, k, x, y) = \text{True if among the first \textbf{j} precincts: \textbf{k} are assigned to } D_1 \text{ and exactly } \\ \textbf{x} 
\text{ vote for } R \text{ in } D_1 \text{ and exactly } \textbf{y} \text{ vote for } R \text{ in } D_2$
- $S(j, k, x, y) = S(j-1, k-1, x-R(p_j), y) \vee S(j-1, k, x, y-R(p_j))$: this is a $D_1$-centric view of the world, and $k$ just represents how many are assigned to $D_1$
- End result is a **bottom-up** quadruple-nested for loop

## Runtime

- $\Theta(n^4m^2)$, where $m^2$ is $2^{2*\text{input size }}$, where the two multiplier in the exponent comes from $m^2$ - **pseudo-polynomial runtime**

# Coins

13. Explain the coin recursive approach, runtime, and base case. Also, how do we prove it?

![coins](https://i.imgur.com/QXVRmrY.png)

- The greedy approach works better if we use just one case (US coins)
- To prove, take it one 'stage at a time', like $0 < x < 5$ for pennies, $5 \le x \le 9$, and so on for nickels

# Interval Scheduling

14. What's the algorithm, and the argument for correctness?

- The algorithm is pick the earliest end time, add it to the solution, remove it and the conflicting events, and return the solution.
- Exchange argument
