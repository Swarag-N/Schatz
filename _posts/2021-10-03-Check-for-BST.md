---
layout: post
title: 
description: 
summary: 
tags:
    - gfg
    - potd
    - python
    - medium
minute: 1
---

## Problem Statement
Given an undirected graph with V vertices and E edges, check whether it contains any cycle or not. 

## Solution
```python
class Solution:
    
    #Function to detect cycle in an undirected graph.
    #def isCycle(self, V, adj):
	
	def isCycle(self, V, adj):
	    #Code here
		vis = [0]*V
		
		def dfs(cur, parent):
		    vis[cur] = 1
		    
		    for i in adj[cur]:
		        if not vis[i]:
		            if dfs(i, cur): return True
		        elif i != parent:
		            return True
		            
		    return False
		
		for i in range(V):
		    if not vis[i]:
		        if dfs(i, -1): return True
		        
		return False
```
