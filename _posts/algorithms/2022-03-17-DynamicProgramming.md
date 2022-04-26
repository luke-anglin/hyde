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
- $\Theta(2n)$ time to update pixels, $\Theta(n+m)$ (where $n$ and $m$ are the rows and columns) to find min and backtrack

# Gerrymandering

- Assigning precincts $\{p_1, p_2 \dots \}$ to two districts $D_1, D_2$

## Consider the last precinct

- Check valid gerrymandering on the two options (assign $p_\text{last}$ to $D_1 \text{ or } D_2$)
- $S(j, k, x, y) = \text{True if among the first \textbf{j} precincts: \textbf{k} are assigned to } D_1 \text{ and exactly } \\ \textbf{x} 
\text{ vote for } R \text{ in } D_1 \text{ and exactly } \textbf{y} \text{ vote for } R \text{ in } D_2$ - uses **top-down**, looks at what would've been necessary to create this state in the $n-1$ step before
- $S(j, k, x, y) = S(j-1, k-1, x-R(p_j), y) \vee S(j-1, k, x, y-R(p_j))$: this is a $D_1$-centric view of the world, and $k$ just represents how many are assigned to $D_1$
- End result is a **bottom-up** quadruple-nested for loop

## Runtime

$\Theta(n^4m^2)$, where $m^2$ is $2^{2*\text{ input size }}$

# Interval Scheduling

## Algo

- Pick earliest end event
- Remove conflicting events
- Repeat

## Exchange argument

![](https://i.imgur.com/a2HQLXv.png)

# Huffman Encoding

## Prefix-Free Code (PFC)

- A codeword table $T$ where $\forall_c \in T, c_1 \neq c_2,$, code($c_1$) is not a prefix of code($c_2$)
- Any PFC can be represented as a binary tree, where the **leaves are the characters**, and vice versa
- Want to minimize $B(T, \{f_c\}) = \sum_c l_c f_c$

## Greedy Huffman Algo

- Choose the least frequent pair, combine into a subtree, reduces problem size by 1.

## Exchange Argument

1. Show any optimal tree is **full**
2. **Claim**: If $c_1, c_2$ are the least-frequent characters, then there is an optimal prefix-free code where $c_1, c_2$ are siblings.
3. **Case 1**: Consider $T_{opt}$, an optimal tree. If $c_1, c_2$ are siblings, the claim holds
4. **Case 2**: If $c_1, c_2$ are not siblings in some $T_opt$, let $a,b$ be the actual two characters of lowest depth that _are_ siblings.

- If $c_1, c_2$ are swapped with $a, b$ then the cost of the tree will not increase because for $a$, we have

$$
B(T_{opt}) = C + f_{c_1}l_{c_1} + f_a l_a  \\
\text{vs. } B(T') = C + f_{c_1}l_{l_a} + f_a l_{c_1}
\\ \text{Is the following postiive or zero? Yes} \\
(f_a - f_{c_1})(l_a - l_{c_1}) \\
B(T_{opt}) - B(T') \ge 0
$$

- We're only swapping the **lengths**, the frequencies remain the same, so the math proves that $T_{opt}$ and $T'$ must be equal or positive


