---
layout: post
title:  Magical Doors
description: Chef wants to cross a hallway of N doors. These N doors are represented as a string. Each door is initially either open or close, represented by 1 or 0 respectively. Chef is required to go through all the doors one by one in the order that they appear, starting from the leftmost door and moving only rightwards at each step.
summary: Chef wants to cross a hallway of N doors. These N doors are represented as a string. Each door is initially either open or close, represented by 1 or 0 respectively. Chef is required to go through all the doors one by one in the order that they appear, starting from the leftmost door and moving only rightwards at each step.
tags:
    - codechef
    - START13C
    - python
    - easy
minute: 1
---

### Problem Statement
Chef wants to cross a hallway of N doors. These N doors are represented as a string. Each door is initially either open or close, represented by 1 or 0 respectively. Chef is required to go through all the doors one by one in the order that they appear, starting from the leftmost door and moving only rightwards at each step.

To make the journey easier, Chef has a magic wand, using which Chef can flip the status of all the doors at once. Determine the minimum number of times Chef has to use this wand to cross the hallway of doors.

For example, the doors are 10011. Chef will start from the left and enter the first door. After passing through that door, the magic wand is waved. This flips the string to 01100. Now Chef passes through the next two doors in one go. Again, just before reaching the 4th door, the magic wand is waved. Now that the string is in its original state, Chef passes through the last two doors as well. The minimum number of times the magic wand needed to be used here was 2.

### Solution
```python
# cook your dish here
T = int(input())
for _ in range(T):
    S = input()
    cnt = 0
    
    if(S[0]=="1"):
        i = 1;
        while(i<len(S)):
            while(i<len(S) and S[i]==S[i-1]):
                i+=1;
            if(i<len(S)):
                cnt+=1
                i+=1;
    else:
        cnt+=1
        i = 1;
        while(i<len(S)):
            while(i<len(S) and S[i]==S[i-1]):
                i+=1;
            if(i<len(S)):
                cnt+=1
                i+=1;
    print(cnt)
```
