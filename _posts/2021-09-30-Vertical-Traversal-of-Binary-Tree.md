---
layout: post
title: Vertical Traversal of Binary Tree
description: Given a Binary Tree, find the vertical traversal of it starting from the leftmost level to the rightmost level. If there are multiple nodes passing through a vertical line, then they should be printed as they appear in level order traversal of the tree.
summary: Given a Binary Tree, find the vertical traversal of it starting from the leftmost level to the rightmost level. If there are multiple nodes passing through a vertical line, then they should be printed as they appear in level order traversal of the tree.
tags:
    - gfg
    - potd
    - java
    - medium
    - note
minute: 1
---

## Problem Statement
Given a Binary Tree, find the vertical traversal of it starting from the leftmost level to the rightmost level.
If there are multiple nodes passing through a vertical line, then they should be printed as they appear in level order traversal of the tree.

### Note
- Check for traversal type asked.

## Solution
```java

//User function Template for Java
class MetaNode{
    Node head;
    int pos;
    MetaNode(Node root,int position){
        head = root;
        pos = position;
    }
}


class Solution
{
    //Function to find the vertical order traversal of Binary Tree.
    static ArrayList <Integer> verticalOrder(Node root){
        // add your code here
        Map<Integer, List <Integer>>  res = new TreeMap<>();
        ArrayDeque<MetaNode> q = new ArrayDeque<>();
        
        MetaNode head = new MetaNode(root,0);
        q.add(head);
        
        while(q.isEmpty()!=true){
            int cnt = q.size();
            for(int i=0;i<cnt;i++){
                MetaNode cur = q.pop();
                if (res.containsKey(cur.pos)!=true){
                    res.put(cur.pos,new LinkedList <Integer>());
                }
                res.get(cur.pos).add(cur.head.data);
                if(cur.head.left!=null){
                    q.addLast(new MetaNode(cur.head.left,cur.pos-1));
                }
                if(cur.head.right!=null){
                    q.addLast(new MetaNode(cur.head.right,cur.pos+1));
                }
            }
        }
        
        ArrayList<Integer> soln =  new ArrayList<Integer>();
        for(List<Integer> temp:res.values()){
            for(Integer val:temp){
                soln.add(val);
            }
        }
        return soln;
    }
}
```
