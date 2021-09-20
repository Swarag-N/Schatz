---
layout: post
title: Factorials of large numbers
description: Given an integer N, find its factorial.
summary: Given an integer N, find its factorial.
tags:
    - gfg
    - potd
    - java
    - python
    - medium
    - appris
    - edge_case
minute: 1
---

### Problem Statement
Given an integer N, find its factorial.

## Appris
- Python is better for these types of problems, datatype overflow will not be an issue.
- Integers in Python 3 are limited only by available memory. Python 2 had two integer types - int and long. They are unified from Python 3.
- BigInteger is an 0ption in Java

## Edge Case
- Factorial problems, look for corner cases of the input range. Look for overflow and run-time errors.

1. ```
1
```
2. ```
2
```
3. ```
50
```


### Solution
#### Java
```java
class Solution {
    static void arrayMultiplication(ArrayList<Integer> res, int factor){
        int carry = 0;
        for(int i=res.size()-1;i>=0;i--){
            int temp = res.get(i)*factor + carry;
            res.set(i, temp%10);
            carry = temp/10;
        }
        while(carry>0){
            res.add(0,carry%10);
            carry = carry/10;
        }
    }
    
    static ArrayList<Integer> factorial(int N){
        //code here
        ArrayList<Integer> res = new ArrayList<Integer>();
        if(N==1 || N==2){
            res.add(N);
            return res;
        }
        
        res.add(2);
        for(int i=3;i<=N;i++){
            arrayMultiplication(res,i);
        }
        
        return res;
    }
}
```

#### Python
```python
class Solution:
    def factorial(self, N):
        #code here
        temp = 1
        for i in range(1,N+1):
            temp*=i;
        
        res = []
        for i in str(temp):
            res.append(i)
        return res;
```
