---
layout: post
title: Dam of Candies
description: Geek wants to make a special space for candies on his bookshelf. Currently, it has N books, each of whose height is represented by the array height[] and has unit width. Help him select 2 books such that he can store maximum candies between them by removing all the other books from between the selected books. The task is to find out the area between two books that can hold the maximum candies without changing the original position of selected books
summary: Geek wants to make a special space for candies on his bookshelf. Currently, it has N books, each of whose height is represented by the array height[] and has unit width. Help him select 2 books such that he can store maximum candies between them by removing all the other books from between the selected books. The task is to find out the area between two books that can hold the maximum candies without changing the original position of selected books
tags:
    - gfg
    - potd
    - python
    - medium
minute: 1
---

### Problem Statement
Geek wants to make a special space for candies on his bookshelf. Currently, it has N books, each of whose height is represented by the array height[] and has unit width.
Help him select 2 books such that he can store maximum candies between them by removing all the other books from between the selected books. The task is to find out the area between two books that can hold the maximum candies without changing the original position of selected books



### Solution
```python
 
class Solution:
    def maxCandy(self, height, n): 
        # Your code goes here
        maximum=0;
        f=0
        l=n-1
        while(f<l):
            if height[f]<height[l]:
                maximum=max(maximum,(l-f-1)*height[f])
                f+=1
            else:
                maximum=max(maximum,(l-f-1)*height[l])
                l-=1
        return maximum
```
