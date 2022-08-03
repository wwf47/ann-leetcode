## Problem
Longest Valid Parentheses
https://leetcode.cn/problems/longest-valid-parentheses/

## Problem Description
```
Given a string containing just the characters '(' and ')', find the length of the longest valid (well-formed) parentheses substring.

Example:
Input: s = "(()"
Output: 2
Explanation: The longest valid parentheses substring is "()".
```

## Code

- Support Language: Python

```
class Solution(object):
    def longestValidParentheses(self, s):
        """
        :type s: str
        :rtype: int
        """
        left, right, maxl = 0, 0, 0
        for i in range(len(s)):
            if s[i]=='(':
                left += 1
            else:
                right +=1
            if left==right:
                maxl = max(maxl, right*2)
            elif left<right:
                left = 0
                right = 0
        left, right = 0, 0
        for i in range(len(s)-1):
            if s[len(s)-i-1] == '(':
                left += 1
            else:
                right += 1
            if left==right:
                maxl = max(maxl, right*2)
            elif left>right:
                left, right = 0, 0
        return maxl
```
