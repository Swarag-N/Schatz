---
layout: post
title: Median of 2 Sorted Arrays of Different Sizes
description: Given two sorted arrays array1 and array2 of size m and n respectively. Find the median of the two sorted arrays.
summary: Given two sorted arrays array1 and array2 of size m and n respectively. Find the median of the two sorted arrays.
tags:
    - gfg
    - potd
    - java
    - python
    - hard
    - appris
    - edge_case
    - note
minute: 1
---

### Problem Statement
Given two sorted arrays array1 and array2 of size m and n respectively. Find the median of the two sorted arrays.

## Appris
- In Python, it is important have integer decimal, as integer itself
``` 
5.0 -> 5
5.1 -> 5.1 
``` 
-  In Java, Divide by double to convert the return into double, rather than type conversion.

## Note
- The naive approach would be to merge the two arrays and return the median element(s). 
- But for the naive method, there is a lot of overhead. We only need the midst element(s). So we could do what we do in merge sort, iterate over the two arrays and have a counter to reach the middle element(s).
- This can be achieved in serval ways, one of which is to create an auxiliary array of size (m + n) /2 +1. (We only need the middle element(s)). Therefore this space is more than enough. 
- But I believe this can be further optimized, by only storing one extra element, in the case of an even number of elements.May reduce the space complexity but not the complexity, cause a check to be done several times

## Edge Case
- Look for <code>Odd</code> and <code>Even</code> number of elements. Check explicitly for even number of total elements

```
4
1 2 3 4
6
5 6 7 8 9 10
```


```
1
4
1
2
```

## Solution
### Java
```java

class GFG 
{ 
    static double medianOfArrays(int n, int m, int a[], int b[]) 
    {
        // Your Code Here
        int mid = ((n+m)/2)+1;
        int[] arr = new int[mid];
        
        int i=0,j=0,k=0;
        
        while(k<mid && i<n && j<m ){
            if(a[i]<=b[j]){
                arr[k++]=a[i++];
            }else{
                arr[k++]=b[j++];
            }
        }
        
        while(k<mid && i<n){
            arr[k++]=a[i++];
        }
        
        while(k<mid && j<m){
            arr[k++]=b[j++];
        }
        
        if((n+m)%2==1){
            return arr[mid-1];
        }else{
            return (arr[mid-1] + arr[mid-2])/2.0;
        }

    }
}
```

#### Python
```python
class Solution:
    def MedianOfArrays(self, array1, array2):
        #code here
        """
        Naive approach
        """
        a = array1+array2
        a.sort();
        
        n = len(a);
        if(n%2==0):
            val = (a[n//2]+a[n//2-1])/2
            if int(val)!=val:
                return val
            else:
                return int(val);
        else:
            return a[n//2];
```