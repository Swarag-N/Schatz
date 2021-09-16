---
layout: post
title: Sort an array of 0s, 1s and 2s
description: Given an array A[] consisting 0s, 1s and 2s. The task is to write a function that sorts the given array. The functions should put all 0s first, then all 1s and all 2s in last.
summary: Given an array of size N containing only 0s, 1s, and 2s; sort the array in ascending order.
tags: gfg potd
minute: 1
---

### Problem Statement
Given an array A[] consisting 0s, 1s and 2s. The task is to write a function that sorts the given array. The functions should put all 0s first, then all 1s and all 2s in last.


## Trivia

This is called as Dutch National Flag Algorithm

### Solution

Code:
```java
class Solution
{
    public static void sort012(int a[], int n)
    {
        // code here 
        int l =0;
        int m =0;
        int f = n-1;
        while(m<=f){
            if(a[m]==0){
                swap(a,m,l);
                m++;
                l++;
            }else if(a[m]==1){
                m++;
            }else if(a[m]==2){
                swap(a,m,f);
                f--;
            }
        }
    }
    private static void swap(int[] arr, int i, int j){
        //3      1        2
        arr[i]=arr[i]+arr[j];
        //1     3        2
        arr[j]=arr[i]-arr[j];
        //2     3        1
        arr[i]=arr[i]-arr[j];
    }
}
```

