## Problem
Merge Two Sorted Lists
https://leetcode.cn/problems/merge-two-sorted-lists/

## Problem Description
```
You are given the heads of two sorted linked lists list1 and list2.
Merge the two lists in a one sorted list. The list should be made by splicing together the nodes of the first two lists.
Return the head of the merged linked list.

Example:
Input: list1 = [1,2,4], list2 = [1,3,4]
Output: [1,1,2,3,4,4]
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
    def mergeTwoLists(self, list1, list2):
        """
        :type list1: Optional[ListNode]
        :type list2: Optional[ListNode]
        :rtype: Optional[ListNode]
        """
        res = ListNode(None)
        l = res
        while list1 and list2:
            if list1.val<list2.val:
                l.next = list1
                list1 = list1.next
            else:
                l.next = list2
                list2 = list2.next
            l = l.next
        if list1:
            l.next = list1
        if list2:
            l.next = list2
        return res.next
```
