---
layout: post
title: K-th element of two sorted Arrays 
description: Given two sorted arrays arr1 and arr2 of size N and M respectively and an element K. The task is to find the element that would be at the k’th position of the final sorted array.
summary: Given two sorted arrays arr1 and arr2 of size N and M respectively and an element K. The task is to find the element that would be at the k’th position of the final sorted array. 
tags: gfg potd
minute: 1
---

### Problem Statement
Given two sorted arrays arr1 and arr2 of size N and M respectively and an element K. The task is to find the element that would be at the k’th position of the final sorted array.  

### Edge Cases
- What if arrays are sorted and given.

```text
5 7 6
72 86 100 112 113
119 256 265 349 445 770 892
```



### Solution
Code:

```java
class Solution {
    public long kthElement( int arr1[], int arr2[], int n, int m, int k) {
        int a1 = 0;
        int a2 = 0;
        boolean flag = true;
        
        for(int i=0;i<k;i++){
            if(a1>=n){
                flag = false;
                a2++;
            }else if (a2>=m){
                flag = true;
                a1++;
            }else{
                if(arr1[a1]<=arr2[a2]){
                    flag=true;
                    a1++;
                }else{
                    flag=false;
                    a2++;
                }
            }
        }
        if(flag){
            return  arr1[a1-1];
        }else{
            return arr2[a2-1];
        }
    }
}
```