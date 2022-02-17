---
layout: post
categories: algorithms
title: Lower Bound Proofs
link: https://uva-cs.github.io/cs4102-s22/slides/cs4102_L8_Hott.pdf
---

## Find Min, Lower Bound Proof

Show that finding the min of an unordered list requires $\Omega(n)$ comparisons

FSORC assume there is an algo that does in less than $n \over 2$ comparisons. Then one element won't be compared, so we can't know we have the minimum $\square$.

## Comparison based sort are $\Omega(n \log n)$

Decision tree strategy

- All permutations are the leaf nodes ($n!$ leaf nodes)
- Tree height is $\log n! $ which is $O (n \log n)$
- If the shortest path is $\log n!$ , then we can do no better than $n \log n$ so that's why we're ultimately $\Omega(n \log n)$
