---
layout: post
title: The Preparations
description: Chef has an exam which will start exactly M minutes from now. However, instead of preparing for his exam, Chef started watching Season-1 of Superchef. Season-1 has N episodes, and the duration of each episode is K minutes.
summary: Chef has an exam which will start exactly M minutes from now. However, instead of preparing for his exam, Chef started watching Season-1 of Superchef. Season-1 has N episodes, and the duration of each episode is K minutes.
tags:
    - codechef
    - START13C
    - python
    - easy
minute: 1
---

### Problem Statement
Chef has an exam which will start exactly M minutes from now. However, instead of preparing for his exam, Chef started watching Season-1 of Superchef. Season-1 has N episodes, and the duration of each episode is K minutes.

Will Chef be able to finish watching Season-1 strictly before the exam starts?


### Solution
```python
# cook your dish here
T = int(input())
for _ in range(T):
    M,N,K = list(map(int,input().split(" ")))
    
    if M>(N*K):
        print("YES")
    else:
        print("NO")
```
