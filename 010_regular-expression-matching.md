## Problem
Regular Expression Matching
https://leetcode.cn/problems/regular-expression-matching

## Problem Description
```
Given an input string s and a pattern p, implement regular expression matching with support for '.' and '*' where:

'.' Matches any single character.
'*' Matches zero or more of the preceding element.
The matching should cover the entire input string (not partial).

Example:
Input: s = "aa", p = "a"
Output: false
Explanation: "a" does not match the entire string "aa".
```

## Code

- Support Language: Python
1. 正则表达式
```
import re
class Solution(object):
    def isMatch(self, s, p):
        """
        :type s: str
        :type p: str
        :rtype: bool
        """
        return re.match('^'+p+'$',s)!=None
```
2. 递归
```
class Solution(object):
    def isMatch(self, s, p):
        """
        :type s: str
        :type p: str
        :rtype: bool
        """
        if not s and not p:
            return True
        if len(s)>0 and len(p)==0:
            return False
        if len(p)>1 and p[1] == "*":
            if len(s)>0 and (s[0]==p[0] or p[0]=='.'):
                return self.isMatch(s[1:], p) or self.isMatch(s, p[2:])
            else:
                return self.isMatch(s, p[2:])
        if len(s)>0 and (s[0]==p[0] or p[0]=='.'):
            return self.isMatch(s[1:], p[1:])
        else:
            return False
```
