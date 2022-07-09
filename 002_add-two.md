
## Problem
Add Two Numbers
https://leetcode.cn/problems/add-two-numbers

## Problem Description
```
You are given two non-empty linked lists representing two non-negative integers. The digits are stored in reverse order, and each of their nodes contains a single digit. Add the two numbers and return the sum as a linked list.
You may assume the two numbers do not contain any leading zero, except the number 0 itself.

Example

Input: l1 = [2,4,3], l2 = [5,6,4]
Output: [7,0,8]
Explanation: 342 + 465 = 807.
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
    def addTwoNumbers(self, l1, l2):
        """
        :type l1: ListNode
        :type l2: ListNode
        :rtype: ListNode
        """
        head = ListNode(0)
        tail = head
        count = 0

        while l1 or l2:
            x = l1.val if l1 else 0
            y = l2.val if l2 else 0

            r = count + x + y
            count = r//10
            tail.next = ListNode(r%10)
            tail = tail.next
            if l1!=None:
                l1 = l1.next
            if l2!=None:
                l2 = l2.next
        if count>0:
            tail.next = ListNode(1)
        return head.next
```


