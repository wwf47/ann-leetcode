## Problem
Implement strStr()
https://leetcode.cn/problems/implement-strstr/

## Problem Description
```
Implement strStr().
Given two strings needle and haystack, return the index of the first occurrence of needle in haystack, or -1 if needle is not part of haystack.
Clarification:

What should we return when needle is an empty string? This is a great question to ask during an interview.
For the purpose of this problem, we will return 0 when needle is an empty string. This is consistent to C's strstr() and Java's indexOf().

Example:
Input: haystack = "hello", needle = "ll"
Output: 2
```

## Code

- Support Language: Python

```
class Solution(object):
    def strStr(self, haystack, needle):
        """
        :type haystack: str
        :type needle: str
        :rtype: int
        """
        return haystack.find(needle)
```
