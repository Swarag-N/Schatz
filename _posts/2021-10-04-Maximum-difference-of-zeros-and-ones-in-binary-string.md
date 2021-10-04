---
layout: post
title: Maximum difference of zeros and ones in binary string
description: iven a binary string S consisting of 0s and 1s. The task is to find the maximum difference of the number of 0s and the number of 1s (number of 0s – number of 1s) in the substrings of a string. 
summary: iven a binary string S consisting of 0s and 1s. The task is to find the maximum difference of the number of 0s and the number of 1s (number of 0s – number of 1s) in the substrings of a string.
tags:
    - gfg
    - potd
    - java
    - medium
    - dp
    - appris
    - edge_case
    - note
minute: 1
---

## Problem Statement
Given a binary string S consisting of 0s and 1s. The task is to find the maximum difference of the number of 0s and the number of 1s (number of 0s – number of 1s) in the substrings of a string.

Note: In the case of all 1s, the answer will be -1.

### Appris
- Application of Kadan Algorithim

### Edge Case
```
00000
```


## Solution
```java
class Solution {
    int maxSubstring(String S) {
        // code here
        int val = 0;
        int res = 0;
        for(int i=0;i<S.length();i++){
            if(S.charAt(i)=='0'){
                val++;
            }else{
                val--;
            }
            res = Math.max(val,res);
            if(val<0){
                val=0;
            }
        }
        if(val ==0 && res ==0){
            return -1;
        }
        return res;
    }
}
```
