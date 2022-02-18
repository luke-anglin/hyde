---
layout: post
title: Unit A Study Guide Questions
categories: algorithms
---

# Asymptotics

1. Give the three cases of the master theorem
2. Provide the limit cases for asymptotics

# Sorting

1. Give the asymptotic runtime of **adjacent sorts**
2. List the five properties of sorting algorithms (not including **online**)
3. Give the satisfied properties for the following sorting algos:
   - Merge sort
   - Quicksort
   - Bubble sort
   - Insertion sort
   - Heap sort
4. Explain in simple English the `Partition` algorithm that `Quicksort` uses
5. When analyzing quicksort using median of medians, why can we add $S(0.7n)$ and $S(0.2n)$ in our analysis?
6. What are the disadvantages of counting sort and radix sort, respectively (i.e. why not use these linear time sorts?)
7. Explain how insertion sort, bubble sort, and heap sort function (just give the general algorithm)

## Lower bound proofs

1. Explain why `findMin` is $\Omega(n)$ with a lower bound proof (can be simple words for studying)
2. Give the general idea of why comparison-based sorting algorithms are $\Omega(n \log n)$
