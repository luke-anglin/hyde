---
layout: post
title: Greedy Algos and Sorting
categories: algorithms
link: https://uva-cs.github.io/cs4102-s22/slides/cs4102_L6_qs-MM-LB-proof.pdf
---

# Greedy Algorithm

- Chooses what's best _right now_ and doesn't look into the future
- Suitable for **optimization problems**
- Our solution to the **coin problem** was greedy

# Sorting

- **Adjacent sort** - always $\Omega(n^2)$ and can never be $o(n^2)$ (ex. the stable insertion sort)

## Inversions

- An out-of-order pair
- Max of $\frac{n(n-1)}{2}$ inversions
- Every swap **fixes only one inversion**

## Insertion Sort

- Insertion sort is an optimal solution for adjacent elements, because it runs in $O(n^2)$

# Quicksort

Worst case $O(n^2)$, best is $O(n\ \text{log}(n))$

**Partition recursively on sublists**

## Partition

- $\Theta(n)$ best case, $\Theta(n^2)$ worst case

![Partition](https://i.imgur.com/se31YTA.png)
![P2](https://i.imgur.com/pCfU5l0.png)

### Quickselect - want $\Theta(n)$ median selection

#### Before MoM

- Finds $i$th smallest element
- Same runtimes as `Partition`, worst case $O(n^2)$ general $O(n)$

#### Median of Medians (MoM)

Break list into chunks of size 5. $n\over 5$ chunks

- Find median of each of these chunks - brute sort and return middle element
- Return median of medians (using Quickselect for $n\over 2$ statistic)

##### Why is this good?

- Remember the top four in teh top right corner and the bottom left four corner are the 40% you don't know about

#### Quickselect with Median of Medians Runtime

- Divide - select an element $p$ using median of medians (i.e. `Partition(p)`) - this is $\Theta(n)$
- Conquer - $\le S(\frac{7}{10} n )$
- Combine - Nothing

Total - $\Theta(n)$

$$
S(n) = S(7n/10) + S(2n/10) + \Theta(n) \le S(9n/10) + \Theta(n)
$$

- This works because we can still be less than it because $f(n+m) \ge f(n) + f(m)$
- Random is better than this generally
- Quicksort generally faster than merge sort

#### Steps

- Partition using median of medians index
- If $i$ is less than the index of the partition, go left
- Otherwise, go right

![Quickselect](https://i.imgur.com/FvJahqe.png)
