## Problem
Swap Nodes in Pairs
https://leetcode.cn/problems/swap-nodes-in-pairs/

## Problem Description
```
Given a linked list, swap every two adjacent nodes and return its head. You must solve the problem without modifying the values in the list's nodes (i.e., only nodes themselves may be changed.)

Example:
Input: head = [1,2,3,4]
Output: [2,1,4,3]
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
    def swapPairs(self, head):
        """
        :type head: ListNode
        :rtype: ListNode
        """
        res = ListNode(0)
        res.next = head
        arr = res
        while arr.next and arr.next.next:
            n1 = arr.next
            n2 = arr.next.next
            arr.next = n2
            n1.next = n2.next
            n2.next = n1
            arr = n1
        return res.next
```
