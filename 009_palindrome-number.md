## Problem
Palindrome Number
https://leetcode.cn/problems/palindrome-number

## Problem Description
```
Given an integer x, return true if x is palindrome integer.
An integer is a palindrome when it reads the same backward as forward.
For example, 121 is a palindrome while 123 is not.

Example:
Input: x = 121
Output: true
Explanation: 121 reads as 121 from left to right and from right to left.
```

## Code

- Support Language: Python

```
class Solution(object):
    def isPalindrome(self, x):
        """
        :type x: int
        :rtype: bool
        """
        if x<0:
            return False
        if x<10:
            return True
        l = 0
        
        tem='%d' %x
        if tem == tem[::-1]:
            return True
        else:
            return False
```
