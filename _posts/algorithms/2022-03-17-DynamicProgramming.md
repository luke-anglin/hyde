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
