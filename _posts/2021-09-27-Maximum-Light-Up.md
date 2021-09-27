---
layout: post
title: Maximum Light Up
description: Chef has allocated himself a budget of P rupees to buy Diwali crackers. There are only 3 types of crackers available in the market and each type of cracker can be bought any number of times.
summary: Chef has allocated himself a budget of P rupees to buy Diwali crackers. There are only 3 types of crackers available in the market and each type of cracker can be bought any number of times.
tags:
    - codechef
    - START13C
    - python
    - easy
minute: 1
---

### Problem Statement
Chef has allocated himself a budget of P rupees to buy Diwali crackers. There are only 3 types of crackers available in the market and each type of cracker can be bought any number of times.

Fuljhari, where each costs a rupees
Anar, where each costs b rupees
Chakri, where each costs c rupees
The crackers have the following interesting properties:-

A Fuljhari can be lit on its own
To light an Anar, you will need x Fuljharis
To light a Chakri, you will need y Fuljharis
What's the maximum total of Anars and Chakris that Chef can light up with his given budget.

### Solution
```python
# cook your dish here
T = int(input())
for _ in range(T):
    P,a,b,c,x,y = list(map(int,input().split(" ")))
    b = b+a*x;
    c = c+a*y;
    
    cnt = 0
    if(P//b > P//c):
        cnt+= P//b
        rem = P - (P//b * b)
        cnt += rem//c
    else:
        cnt+= P//c
        rem = P - (P//c * c)
        cnt += rem//b
    
    print(cnt)
```
