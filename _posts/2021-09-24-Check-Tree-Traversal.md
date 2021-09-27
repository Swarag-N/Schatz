---
layout: post
title: Check Tree Traversal
description: Given Preorder, Inorder and Postorder traversals of some tree of size N. The task is to check if they are all of the same tree or not.
summary: Given Preorder, Inorder and Postorder traversals of some tree of size N. The task is to check if they are all of the same tree or not.
tags:
    - gfg
    - potd
    - java
    - hard
    - note
minute: 1
---

### Problem Statement
Given Preorder, Inorder and Postorder traversals of some tree of size N. The task is to check if they are all of the same tree or not.

### Note
This Soln is By <code>Ayush Modi</code>
https://auth.geeksforgeeks.org/user/ritumodi5/profile


### Solution
```java
class Tree{
    int val;
    Tree left, right;
    Tree(int val){
        this.val = val;
        left = null; right = null;
    }
}

class Solution{
    static int idx;
    static boolean isPossible;
    static boolean checktree(int preorder[], int inorder[], int postorder[], int N){
        idx = 0;
        isPossible = true;
        Map<Integer, Integer> hmap = new HashMap<>();
        for(int i = 0; i < inorder.length; i++) hmap.put(inorder[i], i);
        
        Tree root = buildTree(inorder, preorder, hmap, 0, N-1);
        if(!isPossible) return false;
        List<Integer> post = new ArrayList<>();
        buildPost(root, post);

        return Arrays.equals(post.stream().mapToInt(i->i).toArray(), postorder);
    }
    
    private static void buildPost(Tree root, List<Integer> post){
        if(root == null) return;
        buildPost(root.left, post);
        buildPost(root.right, post);
        post.add(root.val);
    }
    
    private static Tree buildTree(int[] inorder, int[] preorder, Map<Integer, Integer> hmap, int start, int end){
        if(start > end) return null;
        if(!isPossible) return null;
        int val = preorder[idx++];
        Tree root = new Tree(val);
        if(!hmap.containsKey(val)){
            isPossible = false;
            return null;
        }
        int pos = hmap.get(val);
        if(pos < start || pos > end){
            isPossible = false;
            return null;
        }
        root.left = buildTree(inorder, preorder, hmap, start, pos-1);
        root.right = buildTree(inorder, preorder, hmap, pos+1, end);
        return root;
    }
    
}

```
