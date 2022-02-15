---
layout: post
title: Reading - Asymptotics, D&C, Recurrence Relation
categories: algorithms
link: https://uva-cs.github.io/cs4102-s22/slides/cs4102_L3_sorting_intro.pdf
---

$g(n)$ is the function in the parentheses and the one we multiply by $c$, like $\Theta(g(n))$, and $f(n)$ is the function we want to see if is in that set

![Graphs](https://i.imgur.com/whrgy9f.png)

# Easy way to prove

![Limits](https://i.imgur.com/7GNL72X.png)

# Big Theta Notation

![Big Theta](https://i.imgur.com/aMCd9W3.png)

- We say $g(n)$ is an **asymptotic tight bound** for $f(n)$
- Must be **asymptotically nonnegative**

# Little o

Defines a 'not asymptotically tight' Big O. So, $n^2 \neq o(n^2)$, but $n =o(n^2)$.

![](https://i.imgur.com/P7uRbEh.png)

Main difference is definition is that for little $o$ it holds for _all_ c whereas Big O holds for _some_ $c$.

## Proving

When proving, define $c$ in terms of $n_0$

![proof](https://i.imgur.com/jm9sEyK.png)

# Little $\omega$

little $\omega$ is analagous as little o is to big o, and it's definition is like so:

![](https://i.imgur.com/AmLwSMX.png)

# Comparing Asymptotics

- **All** are transitive
- **Big** asymptotics are reflexive
- $\Theta$ is symmetrical - $f(n) = \Theta(g(n)) \leftrightarrow g(n) = \Theta(f(n))$
- $O$ and $\Omega$, and $o$ and $\omega$ are transpose symmetrical pairs, that is, $f(n) = O(g(n)) \leftrightarrow g(n) = \Omega(f(n))$

![](https://i.imgur.com/ByEjsCq.png)

The difference between that image and real numbers is that for reals something has to be $<, =, >$ but for asymptotics it doesn't.

# Montonocity, Strictly In(De)creasing

- Monotonically increases - for every input greater than the last, increases or stays the same
- Strictly increases - for every input greater than the last, increases

# Divide and Conquer

## Maximum subarray

- Used for finding greatest change between a `vector< pair< Day, Price >` for stocks

Consider the 3 cases after division

- In left side entirely
- Right side entirely
- Crossing midpoint

### Crossover Function

- Start from mid and span left and right

![Crossover](https://i.imgur.com/0UFznB2.png)

### Find Max Subarray

1. Divide the array into two parts
2. Figure out if the max subarray is in the left, right, or crossover section
3. Return the sum of that section

![MaxSub](https://i.imgur.com/Iaj8Suq.png)

- Line 1 - Base Case
- Line 3 - Divide
- Line 4-5 = Conquer
- Line 6-11 - Combine (because line 6 does not create a smaller problem)

### Running Time

Runs in $\Theta(nlog(n))$ - $n$ time on each tree level for combine, and $log(n)$ tree levels

![Rec Tree](https://cdn.kastatic.org/ka-perseus-images/5fcbebf66560d8fc490de2a0d8a0e5b1d65c5c54.png)

## Closest points

![](https://i.imgur.com/wqhGcU0.png)

## Matrix Multiplication - Divide and Conquer

![matmul](https://miro.medium.com/max/1400/1*D_1tbv_wNFJ-rrremAGX4Q.png)

![matmul2](https://i.imgur.com/aIVCZDK.png)

### Partition

Partition into $n/2$ by $n/2$

![Partitioning](https://i.imgur.com/MCEULPl.png)

### Naïve Recursive Solution

![Conquer](https://i.imgur.com/H33VYfR.png)

### Running Time

Runs in $\Theta(n^3)$, no faster than the nested for loop solution

### Strassen's D&C Solution

1. Divide inputs $A$ and $B$ and output $C$ into $n/2 \times n/2$ matrices. These are called **submatrices**.
2. Create 10 matries $S_1, S_2, \dots , S_n$, each $n/2 \times n/2$ and being the sum/difference of two matrices created in step 1.
3. Using the submatrices from step 1 and the 10 new marices, recursively compute 7 matric products $P_i$, each $n/2 \times n/2$
4. Add and subtract $P_i$ matrices appropriately to compute the submatrices.

It's almost impossible to know how to do Strassen's algorithm intuitively, so instead reference the book when you need details on coding it out.

**Running time** - $\Theta(n^{2.81})$

# Recurrence Relations

## Methods

- Substitution - guess bound, prove correct/incorrect
- Recursion tree
- Master,
  - Works for recurrences of form $T(n) = aT(n/b) + f(n)$ where $a>=1, b>1$
  - $a$ subproblems, each $1/b$ size of the original problem
  - The divide + combine steps take $f(n)$ time total

## Substitution Method

### Induction Review

![Induct](https://i.imgur.com/L2JC7VY.png)

### Steps

1. Guess something asymptotic like $\Theta(nlog(n))$
2. Sub it in for the recurrent part, making sure to multiply by $c$
3. Test if it holds

![Image](https://i.imgur.com/WovGHdI.png)

### Warnings

- May have to revise inductive hypothesis for boundary conditions (if $T(1)$ doesn't work you might have to say something like for $n > 3$ or $n>2$)
- Sometimes you're left with a constant, like if you're trying to prove for $O(n)$ and you get $T(n) = cn + 1$, don't try to do $n^2$ next. Subtract a lower order term. Example below

![](https://i.imgur.com/5brIAm7.png)

Now, that works for any $d>=1$

#### Asymptotic Pitfall

Need _exact_ form

![](https://i.imgur.com/SYPYOvs.png)

## [Recursion Tree](https://www.youtube.com/watch?v=sLNPd_nPGIc&ab_channel=JohnBowers) - Video

The non-recursive part is the root, the rest is how you divide the tree. Example: for $3T({n/4})+cn^2$, we create **3 subtrees** of size $n/4$ and at the root is $cn^2$

![](https://i.imgur.com/dKMhRZa.png)

- $log_4$ because subproblem is divided by 4 at each level
- Height of a tree is $log_{b}n$

## Master Theorem

![](https://i.imgur.com/WEyekqG.png)

![Master school](https://i.imgur.com/OlKVfMB.png)

### Process

- **Always ask the question: How does $f(n)$ compare to $n^{log_b(a)}$?**
- For case 3 ($\Omega$), show that $af(\frac{n}{b}) \le cf(n)$
