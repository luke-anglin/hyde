---
layout: post 
title: Asymptotic Complexity
category: cs2150
---

## Properties

* Adding Big O - $O(f + g) = O(max(f, g))$
* All are **transitive**
* All are **reflexive**, e.g. $f \in \Omega(f)$
* Only $\Theta$ is **symmetric**, e.g. if $f \in \Theta (g)$, then $g \in \Theta (f)$
* $\Theta$ defines an **equivalence** 

## Function Classification

![Functions](/static/assets/media/functions2.png)

Exponential functions **always** grow **faster** than powers of $n$, so $n^k \in o(c^n)$

## Big $O$ Calculations 

* Consecutive statements - sum of each statement's **max runtime**
* `if` `else` - Time for test plus max of the runtimes 

## Constant 

Input **does not** depend on $n$ 

### Examples

* Getting size of a vector 
* Insertion or removal from a linked list 
* Finding the $k$th element in an array or vector 

## Linear 

Process and perform operation step by step. 

### Examples 

* Printing 
* Finding in arrays, vectors (unsorted) or linked lists (sorted or unsorted)
* Doubling a vector's array 

## Logarithmic 

Running time **cut in half** per iteration 

### Examples 

* Binary search in a sorted array/vector 
* Search in a **balanced tree** 

## Log-Linear 

$\Theta(n \space log(n))$ occurs when you take a linear number of steps, but each one takes $log(n)$ time. 

### Examples 

* Fast sort 
* Quicksort 

## Quadratic 

### Examples 

* Slow sorts, like insertion, bubble and selection 
* Quicksort on a bad day 
* Some graph algorithms 
* Doubly nested loops 

## Exponential

$\Theta(2^n)$, generally trying every solution when there are $2^n$ of them

### Examples

* Binary password cracking
* Traveling salesperson
* Satisfiability of `bool`
