---
layout: post
title: Count distinct elements in every window
description: Given an array of integers and a number K. Find the count of distinct elements in every window of size K in the array.
summary: Given an array of integers and a number K. Find the count of distinct elements in every window of size K in the array.
tags:
    - gfg
    - potd
    - java
    - easy
    - edge_case
minute: 1
---

## Problem Statement
Given an array of integers and a number K. Find the count of distinct elements in every window of size K in the array.


### Edge Case
- Check with window size 1 and N


## Solution
```java
class Solution
{
    ArrayList<Integer> countDistinct(int A[], int n, int k)
    {
        // code here 
        HashMap<Integer,Integer> map = new HashMap<>();
        int i=0;
        for(;i<k-1;i++){
            map.put(A[i],map.getOrDefault(A[i],0)+1);
        }
        
        ArrayList<Integer>  res  = new ArrayList<Integer>();
        
        for(;i<n;i++){
            map.put(A[i],map.getOrDefault(A[i],0)+1);
            
            res.add(map.size());
            
            map.put(A[i-k+1],map.get(A[i-k+1])-1);
            
            if(map.get(A[i-k+1])<1){
                map.remove(A[i-k+1]);
            }
        }
        return res;
    }
}

```
