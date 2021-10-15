---
layout: post
title: All Unique Permutations of an array 
description: Given an array arr[] of length n. Find all possible unique permutations of the array. 
summary: Given an array arr[] of length n. Find all possible unique permutations of the array.
tags:
    - gfg
    - potd
    - python
    - medium
minute: 1
---

## Problem Statement
Given an array arr[] of length n. Find all possible unique permutations of the array.


## Solution
```python
from itertools import permutations
class Solution:
    def uniquePerms(self, arr, n):
        # code here 
        result = []
        per = set(permutations(arr))
        for i in per:
            result.append(i)
        return sorted(result)
```
