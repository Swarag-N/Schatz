---
layout: post
title: Finding middle element in a linked list
description: The task is to complete the function getMiddle() which takes a head reference as the only argument and should return the data at the middle node of the linked list.
summary: The task is to complete the function getMiddle() which takes a head reference as the only argument and should return the data at the middle node of the linked list. 
tags:
    - gfg
    - potd
    - java
    - easy
    - edge_case
minute: 1
---

### Problem Statement
Given a singly linked list of N nodes.
The task is to find the middle of the linked list. For example, if the linked list is
1-> 2->3->4->5, then the middle node of the list is 3.
If there are two middle nodes(in case, when N is even), print the second middle element.
For example, if the linked list given is 1->2->3->4->5->6, then the middle node of the list is 4.

## Edge Case
- Check with Single Element

### Solution
```java
/* Node of a linked list
 class Node {
   int data;
    Node next;
    Node(int d)  { data = d;  next = null; }
}
*/

class Solution
{
    int getMiddle(Node head){
         // Your code here.
        if (head == null ){
            return 0;
        }
        if(head.next ==null){
            return head.data;
        }
        Node fast = head;
        Node slow = head;
        while(fast!=null && fast.next!=null){
            fast = fast.next.next;
            slow = slow.next;
        }
        return slow.data;
    }
}
```
