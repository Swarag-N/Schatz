---
layout: post
title: Count Occurences of Anagrams
description: Given a word pat and a text txt. Return the count of the occurences of anagrams of the word in the text.
summary: Given a word pat and a text txt. Return the count of the occurences of anagrams of the word in the text.
tags:
    - gfg
    - potd
    - java
    - medium
    - note
minute: 1
---

### Problem Statement
Given a word pat and a text txt. Return the count of the occurences of anagrams of the word in the text.

## Note
- Check for substrings not subsequence or subset. [Read Here](https://www.geeksforgeeks.org/subarraysubstring-vs-subsequence-and-programs-to-generate-them/)

### Solution
```java
class Solution {

    int search(String pat, String txt) {
        // code here
        if(pat.length()>txt.length()){
            return 0;
        }
        int a = (int)'a';
        int idx = 0;
        int pl = pat.length();
        int tl = txt.length();
        
        int[] pat_cnt = new int[26];
        int[] txt_cnt = new int[26];
        
        for(;idx<pl;idx++){
            pat_cnt[((int)pat.charAt(idx))-a]++;
            txt_cnt[((int)txt.charAt(idx))-a]++;
        }
        
        int res = 0;
        if(Arrays.equals(pat_cnt,txt_cnt)){
            res++;
        }
        
        for(;idx<tl;idx++){
            txt_cnt[((int)txt.charAt(idx-pl))-a]--;
            txt_cnt[((int)txt.charAt(idx))-a]++;
            
            if(Arrays.equals(pat_cnt,txt_cnt)){
                res++;
            }
        }
        
        return res;
    }
}
```
