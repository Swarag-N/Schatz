---
layout: post
title: Spiral order in matrix.
description: Given an m x n matrix, return all elements of the matrix in spiral order.
summary: Given an m x n matrix, return all elements of the matrix in spiral order.
tags: leetcode
minute: 1
---

### Problem Statement
Given an m x n matrix, return all elements of the matrix in spiral order.

### Edge Cases
- Even and Odd Number of Rows and Columns

```text
[[1,2,3],[4,5,6],[7,8,9],[7,8,9]]
[[1,2,3,4],[5,6,7,8],[9,10,11,12],[9,10,11,12]]
```

### Solution
Code:

```java
class Solution {
    public List<Integer> spiralOrder(int[][] matrix) {
        List<Integer> res = new ArrayList<>();
        
        int n = matrix.length;
        int m = matrix[0].length;
        
        int x0 =0,x1=m-1;
        int y0=0,y1=n-1;
        
        
        while(x0<=x1 && y0<=y1){
            
            for(int i=x0;i<=x1;i++){
                res.add(matrix[y0][i]);
            }
            y0++;
            
            for(int j=y0;j<=y1;j++){
                res.add(matrix[j][x1]);
            }
            x1--;
            
            if(y0<=y1){
                for(int i=x1;i>=x0;i--){
                    res.add(matrix[y1][i]);
                }
            }
            y1--;

            if(x0<=x1){
                for(int j=y1;j>=y0;j--){
                    res.add(matrix[j][x0]);
                }
            }
            x0++;
        }
        return res;
    }
}
```