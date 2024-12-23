---
layout: post
title: Weekly review
tags: [tech, review]
published: false
permalink: /:categories/:year/:month/:day/:title/
---

# Weekly review

## Duration

24-12-15, 24-12-21

## Overview

### Algorithm I

Lecture: advance sort, priority queue, max heap and min heap, top-k, heap sort, A\*

Finished assignment: collinear, 8-puzzle

### Introduction of Database(CS 15445-645)

Lecture: lecture 3 dbms storage of file, pages

Finished assignment: SQL query

### Read & Watch

_仁学_, 谭嗣同: 四十

### No progress field

English, Japanese, Math

## Detail

### Algorithm I

merge sort: according a mid point to compare left part and right part

quicksort: set a **pivot**, usually first or last index, compare every elem with the pivot, the smaller elem on left side, the bigger on right side. **Shuffle** the array before sort to avoid worst case. [Fisher-Yates Shuffle](https://en.wikipedia.org/wiki/Fisher%E2%80%93Yates_shuffle)

worst case of the 2 sort:

quicksort worst case: all elem smaller or bigger than pivot, cause recurse for every elem, **shuffle** before sort to avoid degenerates to quadratic $O(n^2)$.

quicksort for identical elem: 3-way quicksort, use 2 pointers, one for smaller elements, another for identical elements or bigger elements.

merge sort worst case: $\theta(nlogn)$, all cases have same complexity and stable

#### Assignment

Collinear: check if multi points lie on same segment line.

First sort the points by order( the problem give an order definition ), then iterate the array, use an auxiliary array for store points sort by slope with current point, if multi points( more than 3, as the problem ask for at least 4 points ) have a same slope to current point, then add them as a segment( the iterating and greedily adding points avoids problem of adding same segment or its sub-segment).

the complexity is $O(n^2logn)$, the multiply of iterate array and sort( best $O(nlogn)$ )

8-puzzle: find a path from current state to target state, if exists.

The methods is **heuristic** A\* algorithm.
Using a node of tree to represent every state of the current board.
Then, define a heuristic function as a metric of distance from current state to goal state, according the function value, every time select the minimum priority node as next node of path( fullfil with a min heap, priority queue which minimum elem dequeue first), then adds its adjacent nodes to heap, so they become candidate for next time selection. And in theory, constructing a **game tree** store all nodes processed, the leaves are newly added candidates.

The difficult part is how to judge if there is a path to goal state, aka if problem is _solvable_.

To handle this, swap two numbers in the board of state, then check if it is solvable according the A\* in lockstep with original board, if the twin of initial board is solvable, means the original board is unsolvable.

This is based on the _inversion_ number in the current state, same as the term in sort, which means numbers of out of order number pairs. This related to advance math, more info in [Permutation](https://en.wikipedia.org/wiki/Permutation)

The complexity of A\* is varied according implementation. Two optimize methods is

1. avoid add nodes which added before, we can add a ref pointer for parent node to fullfil.

2. caching heuristic function value when we constructed node. It's saved calculation.

more info in [A\*](https://en.wikipedia.org/wiki/A*_search_algorithm)

For Java knowledge, mainly involves OOP inherit, interface, Comparable and Comparator, class of object. For math, involves [total order](https://en.wikipedia.org/wiki/Total_order)

### Introduction of database

As the time organized my folders, I recognized that I try to learn this course 1 year ago, but due to lack persistence and interest, I failed last year.

So this time I am determined to make it.

This week lecture is about storage hierarchy and storage format in physics.

The storage hierarchy can be divided into two parts, the violate and non-violate, ops in cache and in-memo is faster than in network and physics storage like disks.

As the physics storage format, DBMS typically storage record in **File**, which composed by **pages**. Self-contained page is useful for _Backup and Disaster Recovery_( _BDR_ ).

for **page**, the size decides how many records it can load. typically varies from 4KB up to 32KB. Except the file loaded pages as storage, there may also **directory ( special pages )** tracks the location of specific pages in the files.

[Execution of query with storage](/assets/images/weekly_review_24_12_23_disk-oriented%20dbms%20execution.png)

Typical storage format is **slotted pages**, using a slot pointer array to track record's offset from the last record inside the page, and also the used slots. The allocation of space is automatic inside pages.

DBMS keep a unique record id of every logical record reps it physical location. user shouldn't use it.

another storage format of record is **tuple**, composed by **header and attribute data**, constructed with the order given by user when they create tables. Some DBMS may do **denormalize** op, which pre-join some relative tuples and store them together in same page for future use.

**Failsafe**, a feature of DBMS ops, means **ensure database remains operational and consistent if unexpected failures occur**. It related to ACID properties as atomicity, consistency, isolation and durability, and also the transaction. It's critical for DBMS's operation.

$\textbf{\textcolor{orange}{The page is largest physical block of data which device can guarantee failsafe write.}}$

more info ref to lecture notes and slide.

**SQL query** and **SQL Zoo** problems test familiarity of SQL, involves CTE, window function and **execution order of clause** which should be first thing to consider when construct queries. Relate quizzes can be found in assignment repo and SQLZoo page.

### Read and Watch

Tan's thought mixes Buddhism, Confucianism and also refer to Christianism, which mainly based on Buddhism.

He tries to explain the universe and things in terms of so called new knowledge which from western science and technology. And he also shows a tend to idealism based on his Buddhism thinking. Some of his thought is modern, such as sex and commerce. It also exists thinking similar to communism, as total equality of all people without anything be personal property.

He thinks Confucianism is not bad, it should be China's mainstream together with Buddhism, but _Xunzi_ and china's emperors distort original thoughts to rule people, he hope there will some people reform the old Confucianism as a process of nirvana, just like Christianism.

## Next week

db, algo, language, math and seeking job.
