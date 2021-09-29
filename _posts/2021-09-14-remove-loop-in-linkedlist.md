---
layout: post
title: Remove loop in Linked List 
description: This is a collection of short CSS snippets I thought might be useful for beginners
summary: Remove the loop from the linked list, if it is present. 
tags:
    - gfg
    - potd
    - java
    - edge_case
minute: 1
---

## Problem Statement
Given a linked list of N nodes such that it may contain a loop.
A loop here means that the last node of the link list is connected to the node at position X. If the link list does not have any loop, X=0.
Remove the loop from the linked list, if it is present.  

### Edge Cases
- Even Length Circular Linkedlist. 

```text
4
1 2 3 4
1
```

## Solution
Code:

```java
class Solution
{
    //Function to remove a loop in the linked list.
    public static void removeLoop(Node head){
        // code here
        // remove the loop without losing any nodes
        if(head==null || head.next==null){
            return;
        }

        Node fast = head;
        Node slow = head;
        Node prev = head;
        do{
            fast = fast.next.next;
            prev = slow;
            slow = slow.next;
        }while(slow != fast && fast!=null && fast.next!=null);
        
        // check if no loop
        if(fast==null || fast.next == null){
            return;
        }
        
        if(prev.next==head){
            prev.next=null;
            return;
        }

        // even length Circular Linked List Edge Case
        fast = head;
        Node temp=null;
        while(fast!=slow){
            fast=fast.next;
            temp = slow;
            slow=slow.next;
        }
        temp.next = null;
        return;
    }
}
```
