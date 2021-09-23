---
layout: post
title: Count total set bits
description: You are given a number N. Find the total count of set bits for all numbers from 1 to N(both inclusive).
summary: You are given a number N. Find the total count of set bits for all numbers from 1 to N(both inclusive).
tags:
    - gfg
    - potd
    - java
    - medium
minute: 1
---

### Problem Statement
You are given a number N. Find the total count of set bits for all numbers from 1 to N(both inclusive).


### Solution
```java
class Solution{
    
    public static int log2(int N){
  
        // calculate log2 N indirectly
        // using log() method
        int result = (int)Math.floor(Math.log(N) / Math.log(2));
        return result;
    }
    
    //Function to return sum of count of set bits in the integers from 1 to n.
    public static int countSetBits(int n){
        // Your code here
        if((n&(n-1)) == 0){
            //if n is power of 2 directly return result
            return 1+ log2(n)*(n/2);
       }else{
           // y is 2th power  before n
           int y =(int) Math.pow(2,log2(n));
           return (n-y) + countSetBits(y)+ countSetBits(n-y);
       }
    }
}
```
