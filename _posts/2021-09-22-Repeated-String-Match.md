---
layout: post
title: Repeated String Match
description: Given two strings A and B, find the minimum number of times A has to be repeated such that B becomes a substring of the repeated A. If B cannot be a substring of A no matter how many times it is repeated, return -1.
summary: Given two strings A and B, find the minimum number of times A has to be repeated such that B becomes a substring of the repeated A. If B cannot be a substring of A no matter how many times it is repeated, return -1.
tags:
    - gfg
    - potd
    - python
    - medium
    - appris
minute: 1
---

### Problem Statement
Given two strings A and B, find the minimum number of times A has to be repeated such that B becomes a substring of the repeated A. If B cannot be a substring of A no matter how many times it is repeated, return -1.

## Appris
- String questions, Python is goto. 


### Solution
```python
class Solution:
    def repeatedStringMatch(self, A, B):
        # code here
        cnt = 1
        S = A;
        while(len(B) > len(S)):
            S+=A
            cnt+=1
        if B in S:
            return cnt
        if B in S+A:
            return cnt+1
        return -1;
```
