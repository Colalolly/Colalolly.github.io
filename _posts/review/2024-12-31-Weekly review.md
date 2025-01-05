---
layout: post
title: Weekly review
date: 2024-12-31
tags: [tech, review]
permalink: /:categories/:year/:month/:day/:title/
published: false
---

# Weekly review

## Duration

24-12-22, 24-12-28

## Overview

### Algorithm I

started work on tree part, basic binary tree( which populates slots by level ), BST with BFS and DFS

### Database

not much progress, preview and through the last part of storage

### Read & Watch & Writings

_仁学_, 谭嗣同: 四十后

## Detail

### Algorithm I

For BST, use recursive to fullfil construct and update tree.

the average complexity is $O(logN)$ for insert,delete and search

Due to the feature all elements smaller or bigger than the root will be same side, BST may be very unbalanced in some cases, cause the cost of ops degenerate to $O(n)$

for BFS, use queue to store every level's leaf. For DFS, use stack to store leaf and node from one side to another.

Since BST's performance is unstable caused by unbalance, the AVL tree which is auto balancing is a good alternate.

the main ops of AVL tree is auto balancing. The tree do this op when it construct itself. The height of node is set to grow with every level( so the root has smallest height). For every node, the tree keep track it's height, and calculate the height difference between two subtree.

According the insert value and it's relation to current node value, the situation need balancing can be divide in 4 scenarios. The op of rotation in left or right direction will be used to balancing.

The AVL tree avoid disadvantage of standard BST, make the height difference not bigger than 1, ensure a good performance. Complexity of all ops is $\theta(logn)$

### Database

The last module of storage go into more abstract level, the main workload of DBMS been split to two type: OLTP which relates to transaction, involved small batch of data and **write-heavy workload**, OLAP which relates to analytics, involved big chunk of data and **read-heavy workload**. There also hybrid workload consist of read and write .

According to the aim and organization of attributes, there is two type of **storage model**, _Decomposition storage model_ which storage record by column to boost queries execution, dedicated to OLAP workload and _N-ary storage model_ which storage record by row, dedicated to OLTP workload which need fast update of records.

For reduce storage space, dbms often use compression. Dictionary compression is most common.

## TBD

### New year's book list

Following is the _must_ part.
_book about mobilization_
_book about society_
_book about general world history_
Since time is limited, not arbitrary other topics.

### Weekly review

Review is not write down all what learned. Just keep it concise, note key points. First two week's review is too verbose in detail part.
