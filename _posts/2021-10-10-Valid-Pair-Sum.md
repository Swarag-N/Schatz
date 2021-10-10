---
layout: post
title: Valid Pair Sum
description: Given an array of size N, find the number of distinct pairs {i, j} (i != j) in the array such that the sum of a[i] and a[j] is greater than 0.
summary: Given an array of size N, find the number of distinct pairs {i, j} (i != j) in the array such that the sum of a[i] and a[j] is greater than 0.
tags:
    - gfg
    - potd
    - python
minute: 1
---

## Problem Statement
Given an array of size N, find the number of distinct pairs {i, j} (i != j) in the array such that the sum of a[i] and a[j] is greater than 0.


## Solution
Code:

```python

class Solution:
    def ValidPair(self, a, n): 
        # Sorting the given array 
        a = sorted(a) 
  
        # Variable to store the count of pairs 
        ans = 0
  
        # Loop to iterate through the array 
        for i in range(n): 
  
            # Ignore if the value is negative 
            if (a[i] <= 0): 
                continue
  
            # Finding the index using lower_bound 
            j = lower_bound(a,-a[i] + 1) 
  
            # Finding the number of pairs between 
            # two indices i and j 
            ans += i - j 
        return ans
```
