---
layout: post
title: Remove loop in Linked List 
description: This is a collection of short CSS snippets I thought might be useful for beginners
summary: Remove the loop from the linked list, if it is present. 
tags:
    - leetcode
    - leetcode-75
    - python
minute: 1
---

## Problem Statement
Given an array of integers nums, calculate the pivot index of this array.

The pivot index is the index where the sum of all the numbers strictly to the left of the index is equal to the sum of all the numbers strictly to the index's right.

If the index is on the left edge of the array, then the left sum is 0 because there are no elements to the left. This also applies to the right edge of the array.

Return the leftmost pivot index. If no such index exists, return -1.



## Solution


```python
class Solution:
    def pivotIndex(self, nums: List[int]) -> int: 
        aa = 0
        bb = sum(nums)
        
        for i,j in enumerate(nums):
            if aa == (bb-aa-j):
                return i
            aa += j
        return -1
```
