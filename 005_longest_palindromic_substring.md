## Problem
Longest Palindromic Substring
https://leetcode.cn/problems/longest-palindromic-substring

## Problem Description
```
Given a string s, return the longest palindromic substring in s.

Example:
Input: s = "babad"
Output: "bab"
Explanation: "aba" is also a valid answer.

Find the center of the string.

```

## Code

- Support Language: Python

```
class Solution(object):
    def longestPalindrome(self, s):
        """
        :type s: str
        :rtype: str
        """
        if s==None or len(s)<1:
            return ""
        start, end = 0,0
        for i in range(len(s)):
            len1 = self.findCenter(s,i,i)
            len2 = self.findCenter(s,i,i+1)
            lenmax = max(len1,len2)
            if lenmax>end-start:
                start = i-(lenmax-1)//2
                end = i+lenmax//2
        return s[start:end+1]

    def findCenter(self, s, left, right):
        L = left
        R = right
        while (L>=0 and R<len(s)) and s[L]==s[R]:
            L-=1
            R+=1
        return R-L-1
```
