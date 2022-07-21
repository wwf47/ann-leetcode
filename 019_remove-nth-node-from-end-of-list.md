## Problem
Remove Nth Node From End of List
https://leetcode.cn/problems/remove-nth-node-from-end-of-list

## Problem Description
```
Given the head of a linked list, remove the nth node from the end of the list and return its head.

Example:
Input: head = [1,2,3,4,5], n = 2
Output: [1,2,3,5]
```

## Code

- Support Language: Python

```
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution(object):
    def removeNthFromEnd(self, head, n):
        """
        :type head: ListNode
        :type n: int
        :rtype: ListNode
        """
        if not head:
            return None
        l = head
        m = head
        lens = 0
        while l:
            l = l.next
            lens+=1
        if lens == 1 or (lens-n)==0:
            return head.next
        
        for i in range(lens-n-1):
            if m.next:
                m = m.next        
        m.next = m.next.next
        return head
```
