---
layout: post
title: Intersection of Two Arrays II 
description: Given two integer arrays nums1 and nums2, return an array of their intersection. Each element in the result must appear as many times as it shows in both arrays and you may return the result in any order.
summary: Given two integer arrays nums1 and nums2, return an array of their intersection. Each element in the result must appear as many times as it shows in both arrays and you may return the result in any order.
tags:
    - leetcode
    - easy
minute: 1
---

### Problem Statement

Given a linked list of N nodes such that it may contain a loop.
A loop here means that the last node of the link list is connected to the node at position X. If the link list does not have any loop, X=0.
Remove the loop from the linked list, if it is present.  

### Appris

- Streams in Java take much time then simple array value insertion. <code>arr1</code> method took <code>14ms</code>, where as <code>arr2</code> method only took <code>6ms</code>

```java
int[] arr1 = lst.stream().mapToInt(Integer::intValue).toArray();

int arr2[] = new int[lst.size()];
for(int i=0;i<lst.size();i++) {
    arr2[i] = lst.get(i);
}
```
<br>    

### Solution
```java
class Solution {
    public int[] intersect(int[] nums1, int[] nums2) {

        // Map to count frequeny of numbers
        Map<Integer,Integer> map = new HashMap<>();
        
        for(int i:nums1){
            map.put(i,map.getOrDefault(i,0)+1);
        }
        
        // Use Resizeable array, since there may n or m numbers 
        // of numbers in results 
        ArrayList<Integer> lst = new ArrayList<>();
        
        for(int i:nums2){
            // for each number in array 2, update the character 
            // frequency of initial map 
            if(map.containsKey(i)==true && map.get(i)>0){
                lst.add(i);
                map.put(i,map.get(i)-1);
            }
        }
        
        // ArrayList -> Array 
        int arr[] = new int[lst.size()];
        for(int i=0;i<lst.size();i++) {
            arr[i] = lst.get(i);
        }

        return arr;
    }
}
```
