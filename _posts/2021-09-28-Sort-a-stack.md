---
layout: post
title: Sort a stack 
description: Given a stack, the task is to sort it such that the top of the stack has the greatest element.
summary: Given a stack, the task is to sort it such that the top of the stack has the greatest element.
tags:
    - gfg
    - potd
    - java
    - easy
minute: 1
---

### Problem Statement
Given a stack, the task is to sort it such that the top of the stack has the greatest element.

### Solution
```java
class GfG{
	public Stack<Integer> sort(Stack<Integer> s){
		//add code here.
		if (s.isEmpty() != true){
		    Integer temp = s.pop();
		    s = sort(s);
		    sortInsert(s,temp);
		}
		return s;
	}
	
	public void sortInsert(Stack<Integer> s, Integer val){
	    if(s.isEmpty() == true || s.peek() <= val){
	        s.push(val);
	    }else{
	        Integer temp = s.pop();
	        sortInsert(s,val);
	        s.push(temp);
	    }
	}
}
```
