---
layout: post
title: Smallest range in K lists
description: Given K sorted lists of integers, KSortedArray[] of size N each. The task is to find the smallest range that includes at least one element from each of the K lists. If more than one such range's are found, return the first such range found.
summary: Given K sorted lists of integers, KSortedArray[] of size N each. The task is to find the smallest range that includes at least one element from each of the K lists. If more than one such range's are found, return the first such range found.
tags:
    - gfg
    - potd
    - java
    - medium
    - hard
minute: 1
---

## Problem Statement
Given K sorted lists of integers, KSortedArray[] of size N each. The task is to find the smallest range that includes at least one element from each of the K lists. If more than one such range's are found, return the first such range found.

### Note
- This a officail solution given by leetcode editorial
## Solution
```java

class Solution
{
    class Element implements Comparable<Element> {
        int val;
        int ind;
        int row;
        Element (int val, int ind, int row) {
            this.val= val;
            this.ind= ind;
            this.row= row;
        }
        public int compareTo(Element e){
            return this.val- e.val;
        }
    }
	int[] findSmallestRange(int[][] KSortedArray,int n,int k)
	{
	    int length=Integer.MAX_VALUE, low= Integer.MAX_VALUE, high= Integer.MIN_VALUE, max= Integer.MIN_VALUE;
	    PriorityQueue<Element> pq= new PriorityQueue<>();
	    for(int i=0; i<k; i++){
	        max= Math.max(max, KSortedArray[i][0]);
	        pq.add(new Element(KSortedArray[i][0], 0, i));
	    }
	    length= max- pq.peek().val;
	    low= pq.peek().val;
	    high= max;
	   // System.out.println(length + " " + low + " " + high);
	    boolean flag= true;
	    while(flag){
	       // System.out.println(length + " " + low + " " + high);
	        Element x= pq.poll();
	        int row= x.row;
	        int ind= x.ind;
	        if(!(ind+1<n)){
	            flag= false;
	            break;
	        } else {
	            Element ne= new Element(KSortedArray[row][ind+1], ind+1, row);
	            pq.add(ne);
	            max= Math.max(max, KSortedArray[row][ind+1]);
	            if(length> max- pq.peek().val){
	                length= max- pq.peek().val;
	                low= pq.peek().val;
	                high= max;
	            }
	        }
	    }
	    int arr[]= {low, high};
	    return arr;
	}
}
```
