---
layout: post
title: Sorting
categories: algorithms
link: https://uva-cs.github.io/cs4102-s22/slides/cs4102_L6_qs-MM-LB-proof.pdf
---

# Greedy Algorithm

- Chooses what's best _right now_ and doesn't look into the future
- Suitable for **optimization problems**
- Our solution to the **coin problem** was greedy

# Sorting

- **Adjacent sort** - always $\Omega(n^2)$ and can never be $o(n^2)$ (ex. the stable insertion sort)

## Key Properties

- Run time (asymptotic complexity and even constants)
- In place (or in-situ)
- Adaptive - fast if nearly sorted
- Stable
- Parallelizable

### For different Algos

#### Merge Sort

Stable, parallelizable

#### Quicksort

Kinda inplace (uses stack for recursive calls), $O(n \log n)$, parallelizable, better constants than mergesort

#### Bubble sort

In place, stable, $\Theta(n^2)$

#### Insertion Sort

- $\Theta (n^2)$, but with **very small constants**, good for short lists.
- In place, adaptive, stable
- Insertion sort is an optimal solution for adjacent elements, because it runs in $O(n^2)$
  - **Inversions** - an out-of-order pair
  - Max of $\frac{n(n-1)}{2}$ inversions
  - Every swap **fixes only one inversion**
- Online - sort as received

#### Heap Sort

In place

# Quicksort

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


$S(n) = S(7n/10) + S(2n/10) + \Theta(n) \le S(9n/10) + \Theta(n)$


- This works because we can still be less than it because $f(n+m) \ge f(n) + f(m)$
- Random is better than this generally
- Quicksort generally faster than merge sort

#### Steps

- Partition using median of medians index
- If $i$ is less than the index of the partition, go left
- Otherwise, go right

![Quickselect](https://i.imgur.com/FvJahqe.png)

# Linear Time Sorts

## Counting Sort

$O(n+k)$, count how many elements are less than another, insane amount of memory though at $O(n+k)$

![counting](https://cdn.programiz.com/cdn/farfuture/tcfjQdeYwL_jETOCPZxNjIXbysRrb7MaG6PwO2MzHnM/mtime:1582112622/sites/tutorial2program/files/Counting-sort-4_1.png)

## Radix sort

Starting at ones place, sort by digit until max digit

![radix](https://ds055uzetaobb.cloudfront.net/brioche/uploads/IEZs8xJML3-radixsort_ed.png?width=1200)
