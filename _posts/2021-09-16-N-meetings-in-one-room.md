---
layout: post
title: N meetings in one room 
description: Given an array A[] consisting 0s, 1s and 2s. The task is to write a function that sorts the given array. The functions should put all 0s first, then all 1s and all 2s in last.
summary: There is one meeting room in a firm. There are N meetings in the form of (start[i], end[i]) where start[i] is start time of meeting i and end[i] is finish time of meeting i.
tags: coding gfg potd
minute: 1
---

# Question
There is one meeting room in a firm. There are N meetings in the form of (start[i], end[i]) where start[i] is start time of meeting i and end[i] is finish time of meeting i.
What is the maximum number of meetings that can be accommodated in the meeting room when only one meeting can be held in the meeting room at a particular time?



```java
class Solution 
{
    //Function to find the maximum number of meetings that can
    //be performed in a meeting room.
    public static int maxMeetings(int start[], int end[], int n)
    {
        // add your code here
        ArrayList<Meet> schd = new ArrayList<>();
        for(int i=0;i<n;i++){
            schd.add(new Meet(start[i],end[i]));
        }
        Collections.sort(schd,(Meet m1, Meet m2) -> {
            if(m1.e==m2.e){
                return m2.s-m1.s;
            }
            return m1.e-m2.e;
        });
        
        int cnt = 0;
        // System.out.println(schd);
        int l = Integer.MIN_VALUE;
        for(int i=0;i<n;i++){
            if(schd.get(i).s>l){
                l = schd.get(i).e;
                cnt++;
            }
        }
        return cnt;
    }
}
```