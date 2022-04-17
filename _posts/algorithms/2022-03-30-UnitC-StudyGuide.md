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

# Tiling

4. What's the optimal substructure?

`Tile(n-1) + Tile(n-2)`

5. What's the bottom-up approach?

Initialize base cases 0 and 1 with values of 1, and then fill in from $i = 2$ to $n$

# Log Cutting

6. What's the optimal substructure?

- The best cut for the next smallest log size, `max(C[i-j]+p[j])`

7. How do we build the choice array?

Set `choices[i] = j` where $i$ is the log size in the array, which is the index, and $j$ is how far we go back. So if we have a log of size 5 and `choices[5] = 3`, then go back to `choices[2]`, and if that is 2, then you're done.

# Matmul

8. When multiplying two or more matrices, what is the shape of the output?

- The rows of the first one and the columns of the last one

9. How many operations does it take to multiply two matrices?

- The two unmatching parts (rows of the first, columns of the second) multiplied times the matching part (the rows of the second (or cols of first)).

10. What function are we trying to minimize for `Best(i, j)` and what's the runtime?

- `Best(i, k) + Best(k+1, j)` + $r_ir_{k+1}c_j$
- Solve lowest diagonal of a (i, j) or (n, n) diagonal matrix one at a time,
- $\Theta(n^3)$

11. What does `Choice[i, j]` represent in matmul?

- Best split for between matrices $i$ and $j$ was right after $M_k$
  ![](https://i.imgur.com/0l27QBG.png)

# LCS

12. Explain the LCS cases:

- The characters at $i$ and $j$ are equal, so you add one and decrement both.
- They aren't equal, and you take the max of $LCS(i - 1, j), LCS(i, j-1)$

13. LCS runtime?

$\Theta(n*m)$

14. Describe LCS table

- Row and col 0 filled with 0s, where first letter is now at 1 index
- Bottom right stores the length

![](https://i.imgur.com/TWBtVxP.png)

15. Reconstructing LCS approach

- Start in bottom right of memory table
- If symbols match (green), print that symbol and go up or left (may be multiple optimal LCS based on choice here)
- Else, go to largest adjacent (up or left)

# Seam Carving

16. What's the approach and runtime?

- Build a pyramid from top to bottom, saving all pixel values in $M$, three cases for min seam, which is this pixel's value + the min of the $S(n - 1, k \pm 1) \cup S(n-1, k)$
- $\Theta(2n)$ time to update pixels, $\Theta(n+m)$ (where $n$ and $m$ are the rows and columns) to find min and backtrack

# Gerrymandering

17. Explain how we gerrymander (assigning precincts $\{p_1, p_2 \dots \}$ to two districts $D_1, D_2$ with $n$ number of precincts and $m$ mad voters) and it's runtime

- $S(j, k, x, y) = \text{True if among the first \textbf{j} precincts: \textbf{k} are assigned to } D_1 \text{ and exactly } \\ \textbf{x} 
\text{ vote for } R \text{ in } D_1 \text{ and exactly } \textbf{y} \text{ vote for } R \text{ in } D_2$
- $S(j, k, x, y) = S(j-1, k-1, x-R(p_j), y) \vee S(j-1, k, x, y-R(p_j))$: this is a $D_1$-centric view of the world, and $k$ just represents how many are assigned to $D_1$
- End result is a **bottom-up** quadruple-nested for loop

## Runtime

- $\Theta(n^4m^2)$, where $m^2$ is $2^{2*\text{input size }}$, where the two multiplier in the exponent comes from $m^2$ - **pseudo-polynomial runtime**

# Greedy

18. What is a feasible solution?

- Meets some set of constraints

19. What is an objective function?

- Defines what we're trying to optimize for, anything that meets the objective function and is feasible is _an_ optimal solution

# Coins

20. Explain the coin greedy algo, runtime, and base case. Also, how do we prove it?

- $O(k)$ (polynomial, linear) rather than recursive pseudo polynomial $O(k^x)$
- To prove, take it one 'stage at a time', like $0 < x < 5$ for pennies, $5 \le x \le 9$, and so on for nickels, and prove you'd have to use more than the optimal number of the previous coin, like if you didn't use a nickel in range $5 \le x \le 9$ then you'd have to use more than 4 pennies.

# Interval Scheduling

21. What's the algorithm, and the argument for correctness?

- The algorithm is pick the earliest end time, add it to the solution, remove it and the conflicting events, and return the solution.
- Exchange argument
  - $a^*$ is our choice, earliest to end
  - $a$ is the earliest ending $OPT$ choice
  - We know there can't be a conflict because $a^*$ ends earlier and it must be the case that this solution is still optimal if we switch them

# Huffman Encoding

22. What's the objective/optimization function?

Minimizes $\sum_c l_c f_c$

What's the algorithm?

- Greedy, choose least frequent pair, combine into a subtree with root being the sum.

23. Show Huffman is optimal?

- Show there is an optimal tree in which the least frequent characters are siblings - exchange argument
- Show that making them siblings and solving the new smaller sub-problem results in an optimal solution

24. What is necessary to prove a greedy algorithm?

- Prove the greedy property is optimal (exchange argument)
- Prove the optimal substructure works as expected

# Cache Scheduling

25. What's the greedy property?

- Belady evict rule - evict the item accessed farther in the future

26. What's the runtime?

- $\Theta(n^2 k)$, where $k$ is cache space

27. What's the inputs?

$k$ is the size of the cache, $M (m_1, m_2, \dots)$ is the access patterns, minimize cache fetches
