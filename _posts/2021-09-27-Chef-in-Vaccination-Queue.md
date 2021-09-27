---
layout: post
title: Chef in Vaccination Queue 
description: 
summary: 
tags:
    - codechef
    - START13C
    - python
    - easy
minute: 1
---

### Problem Statement
There are N people in the vaccination queue, Chef is standing on the Pth position from the front of the queue. It takes X minutes to vaccinate a child and Y minutes to vaccinate an elderly person. Assume Chef is an elderly person.

You are given a binary array A1,A2,…,AN of length N, where Ai=1 denotes there is an elderly person standing on the ith position of the queue, Ai=0 denotes there is a child standing on the ith position of the queue. You are also given the three integers P,X,Y. Find the number of minutes after which Chef's vaccination will be completed.

### Solution
```python
# cook your dish here2
T = int(input())
for _ in range(T):
    N,P,X,Y = list(map(int,input().split(" ")))
    A = input().split(" ")
    val = 0
    for i in range(0,P):
        if(A[i]=="0"):
           val+=X
        else:
            val+=Y
    print(val)
```
