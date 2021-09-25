---
layout: post
title: Largest subarray with 0 sum 
description: Given an array having both positive and negative integers. The task is to compute the length of the largest subarray with sum 0.
summary: Given an array having both positive and negative integers. The task is to compute the length of the largest subarray with sum 0.
tags:
    - gfg
    - potd
    - java
    - easy
    - appris
minute: 1
---

### Problem Statement
Given an array having both positive and negative integers. The task is to compute the length of the largest subarray with sum 0.

## Appris
- Check whether the prefix sum has appeared earlier, cause  this shows the sum of values between current element and previous is equivalent to zero

### Solution
```java
class GfG
{
    int maxLen(int arr[], int n){
        // Your code here
        Map<Integer, Integer> map = new HashMap<>();
        int sum = 0;
        map.put(sum,0);
        sum+=arr[0];
        
        int res = 0;
        map.put(sum,1);
        
        for(int i=1;i<n;i++){
            sum+=arr[i];
            Integer val = map.get(sum);
            if(val!=null){
                res = Math.max(res,i-val+1);
            }else{
                map.put(sum,i+1);
            }
        }
        
        return res;
    }
}
```
