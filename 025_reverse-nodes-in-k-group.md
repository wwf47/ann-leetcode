## Problem
Reverse Nodes in k-Group
https://leetcode.cn/problems/reverse-nodes-in-k-group/

## Problem Description
```
Given the head of a linked list, reverse the nodes of the list k at a time, and return the modified list.
k is a positive integer and is less than or equal to the length of the linked list. If the number of nodes is not a multiple of k then left-out nodes, in the end, should remain as it is.
You may not alter the values in the list's nodes, only nodes themselves may be changed.

Example:
Input: head = [1,2,3,4,5], k = 2
Output: [2,1,4,3,5]
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
    def reverseKGroup(self, head, k):
        if not head:
            return
        a, b = head, head
        for i in range(k):
            if not b:
                return head
            b = b.next
        # 反转前k个元素
        newhead = self.reverse(a, b)
        a.next = self.reverseKGroup(b, k)
        return newhead

    def reverse(self, l1, l2):
        pre, cur, nxt = None, l1, l1
        while cur != l2:
            nxt = cur.next
            cur.next = pre
            pre = cur
            cur = nxt
        return pre
```
