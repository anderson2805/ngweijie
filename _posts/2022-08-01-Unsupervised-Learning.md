---
title: Unsupervised Learning (Lab)
tags: [Learning, Machine Learning, Artificial Intelligence]
style: fill
color: info
description: RECAP of Deeplearning.AI - Unsupervised Learning
---
## Week 1 - Clustering Lab

[np.linalg.norm](https://numpy.org/doc/stable/reference/generated/numpy.linalg.norm.html) works as the Euclidean distance because it is the l2 norm, and the default value of the ord parameter in numpy.linalg.norm is 2.

![image](https://i.stack.imgur.com/iWe4J.png)

norm_ij = np.linalg.norm(X[i] - centroids[j])  # Your code to calculate the norm between (X[i] - centroids[j])