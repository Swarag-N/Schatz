---
layout: post
title: Check for BST
description: Given the root of a binary tree. Check whether it is a BST or not.
summary: Given the root of a binary tree. Check whether it is a BST or not.
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
Given the root of a binary tree. Check whether it is a BST or not.
Note: We are considering that BSTs can not contain duplicate Nodes.
A BST is defined as follows:
- The left subtree of a node contains only nodes with keys less than the node's key.
- The right subtree of a node contains only nodes with keys greater than the node's key.
- Both the left and right subtrees must also be binary search trees.

### Appris
- Inorder Traversal of Binary Search Tree results sorted array.

### Edge Case
```
3 2 5 1 4
```
Understanding Edge Case
```
        4
      /   \
    2       5
      \
        6
```
### Note
- This is the official solution provided by GeeksForGeeks Editorial


## Solution
1. Efficient Solution

```java
public class Solution
{
    Node prev;
    //Function to check whether a Binary Tree is BST or not.
    boolean isBST(Node root)
    {
        // code here.
        if (root != null)
        {
            if (!isBST(root.left))
                return false;
            
            // allows only distinct values node
            if (prev != null && root.data <= prev.data )
                return false;
            prev = root;
            return isBST(root.right);
        }
        return true;
    }
}
```
2. 🔴🔴🔴 Edge Case Failing Code
```java
public class Solution{ 
    Node prev;
    //Function to check whether a Binary Tree is BST or not.
    boolean isBST(Node root){
        // code here.
        if (root != null){
            /* False if left is > than node */
            if (node.left != null && node.left.data > node.data)
                return false;
            
            /* False if right is < than node */
            if (node.right != null && node.right.data < node.data) 
                return false; 
            
            // allows only distinct values node
            if (prev != null && root.data <= prev.data )
                return false;
            
            prev = root;
            return isBST(root.right);
        }
        return true;
    }
}
```
