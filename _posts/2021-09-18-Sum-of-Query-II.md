---
layout: post
title: Sum of Query II
description: You are given an array arr[] of n integers and q queries in an array queries[] of length 2*q containing l, r pair for all q queries. You need to compute the following sum over q queries.
summary: You are given an array arr[] of n integers and q queries in an array queries[] of length 2*q containing l, r pair for all q queries. You need to compute the following sum over q queries.
tags:
    - gfg
    - medium 
    - potd
minute: 1
---

### Problem Statement
You are given an array arr[] of n integers and q queries in an array queries[] of length 2*q containing l, r pair for all q queries. You need to compute the following sum over q queries.

## Example
- Need to find the sum of numbers between two points
    - why not find complete sum and remove 
        - the staring and
        - the ending sum
    - starting and ending sum can be found out in <code>O(n)<code>

### Solution
```java
class Solution{
    List<Integer> querySum(int n, int arr[], int q, int queries[])
    {
        // code here
        // find prefix_sum and suffix_sum
        int[] preSum = new int[n+1];
        int[] sufSum = new int[n+1];
        
        preSum[0] = 0;
        sufSum[n] = 0;
        int t = 0;
        for(int i=0;i<n;i++){
            preSum[i+1]=arr[i]+preSum[i];
            t+=arr[i];
        }
        
        for(int i=n-1;i>=0;i--){
            sufSum[i]=arr[i]+sufSum[i+1];
        }
        
        List<Integer> res = new ArrayList<>();
        
        for(int i=0;i<2*q;i+=2){
            res.add(t-preSum[queries[i]-1]-sufSum[queries[i+1]]);
        }
        
        return res;
    }
}
```
