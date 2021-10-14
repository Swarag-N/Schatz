---
layout: post
title: Swap all odd and even bits
description: The task is to swap all odd bits with even bits.
summary: The task is to swap all odd bits with even bits.
tags:
    - gfg
    - potd
    - java
    - easy
    - appris
    - edge_case
    - note
minute: 1
---

## Problem Statement
Given an unsigned integer N. The task is to swap all odd bits with even bits. For example, if the given number is 23 (00010111), it should be converted to 43(00101011). Here, every even position bit is swapped with adjacent bit on the right side(even position bits are highlighted in the binary representation of 23), and every odd position bit is swapped with an adjacent on the left side.

### Appris
- Refeesfhed about data 
### Edge Case
- Check with numbers other greater than <code>10<sup>9</sup></code> like <code>2<sup>31</sup></code> and  <code>2<sup>32</sup></code> 
 
### Notes
- Refer Java Docs for [Integer Parse Method](https://docs.oracle.com/javase/7/docs/api/java/lang/Integer.html#parseInt(java.lang.String,%20int))
- Refer Java Docs of [String Builder](https://docs.oracle.com/javase/7/docs/api/java/lang/StringBuilder.html#setCharAt(int,%20char))

## Solution
```java
class Solution{
    //Function to swap odd and even bits.
    public static int swapBits(int n) 
    {
	    // Your code
	    String s = Integer.toBinaryString(n);
	    StringBuilder sb = new StringBuilder(s);
	    if(s.length()%2==1 && sb.length()<31){
	        sb.insert(0,"0");
	    }
	    
	    for(int i=0;i<s.length();i+=2){
	        char temp = sb.charAt(i);
	        sb.setCharAt(i,sb.charAt(i+1));
	        sb.setCharAt(i+1,temp);
	    }
	    String e = sb.toString();
	    
	    int res = Integer.parseInt(e, 2);
	    return res;
	}
    
}
```
