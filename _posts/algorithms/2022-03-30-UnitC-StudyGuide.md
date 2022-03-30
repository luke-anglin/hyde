---
layout: post
title: Unit C Study Guide
categories: algorithms
---

# Dynamic Programming Slidesets

1. [Log-cutting](https://uva-cs.github.io/cs4102-s22/slides/cs4102-C-lecture1.pdf)
2. [Matrix Mult, LCS](https://uva-cs.github.io/cs4102-s22/slides/cs4102-C-lecture2-3.pdf)

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
