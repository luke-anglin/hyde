---
layout: post
title: Dynamic Programming
categories: algorithms
---

- Uses **memoization** to save values for later computations
- Requires an **optimal substructure** - solutions to larger problems use smaller optimal solutions

## Strategy

1. Identify the recursive structure - what is the last thing done?
2. Save solutions in memory
3. Choose **top down** for recursive solutions, and **bottom up** for iterative approaches

# Matrix Multiplication

## How many multiplications

- Multiply the unique numbers by one of the same numbers
  - Example - For matrices $(1,2), (2, 3)$ you'd do 1*2*3
  - To do three,consider that as a single $(1,3)$ matrix, and add the operations for multiplying by some other matrix, say $(3, 1)$. You'd end up with 1*2*3+1*3*1
  - Formula from class $c_1*r_1*c_3 + c_2*r_2*c_3 = c_3*(r_1*c_1+r_2*c_2)$

## `Best`

- Base case - `Best(i, i+1)`

## Recursive Definition

**Store those `Best(i, j)` values in memory!**

![Recursive Def](https://i.imgur.com/v9nMWU7.png)

## Choice table

- `Choice[i,j]` means best split was right after $M_k$
- So you may have `Choice[1,6]` and then need `Choice` of smaller subproblems

## Run Time

$\Theta(n^3)$, because we have $\Theta(n^2)$ cells in the `Best` table,and have $\Theta(n)$ options for each cell

# LCS Recursive Approach

![LCS Recursion](https://i.imgur.com/2ebKEOh.png)

## LCS Dynamic Programming - Just getting Length

![LCS DP](https://i.imgur.com/jOE8WM8.png)

### Runtime

$\Theta(n*m) \text{ for } |X| = n, |Y| = m$

## Reconstructing the actual LCS

- Start in bottom right (finished) position
- If symbols match (green) then go diagonal
- Else go to the largest adjacent (up or left, never right or down) character

# Seam Carving

- Build a pyramid from top to bottom, saving all pixel values in $M$
- $\Theta(2n)$ time to update pixels, $\Theta(n+m)$ (where $n$ and $m$ are the rows and columns)

# Gerrymandering

- Assigning precincts $\{p_1, p_2 \dots \}$ to two districts $D_1, D_2$

## Consider the last precinct

- Check valid gerrymandering on the two options (assign $p_\text{last}$ to $D_1 \text{ or } D_2$)
- $S(j, k, x, y) = \text{True if among the first \textbf{j} precincts: \textbf{k} are assigned to } D_1 \text{ and exactly } \\ \textbf{x} 
\text{ vote for } R \text{ in } D_1 \text{ and exactly } \textbf{y} \text{ vote for } R \text{ in } D_2$ - uses **top-down**, looks at what would've been necessary to create this state in the $n-1$ step before
- $S(j, k, x, y) = S(j-1, k-1, x-R(p_j), y) \vee S(j-1, k, x, y-R(p_j))$: this is a $D_1$-centric view of the world, and $k$ just represents how many are assigned to $D_1$
- End result is a **bottom-up** quadruple-nested for loop ~ $\Theta(n^4)$
