## Problem
Valid Parentheses
https://leetcode.cn/problems/valid-parentheses

## Problem Description
```
Given a string s containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.
An input string is valid if:
1. Open brackets must be closed by the same type of brackets.
2. Open brackets must be closed in the correct order.

Example:
Input: s = "()"
Output: true
```

## Code

- Support Language: Python
- stack

```
class Solution(object):
    def isValid(self, s):
        """
        :type s: str
        :rtype: bool
        """
        m = []
        l = ["(", "[", "{"]
        r = [")", "]", "}"]
        for i in range(len(s)):
            if m and s[i] in r:
                ii = r.index(s[i])
                if m[-1]==l[ii]:
                    m.pop()
                else:
                    return False
            else:
                m.append(s[i])
        if not m:
            return True
        else:
            return False
```
- replace string
```
class Solution(object):
    def isValid(self, s):
        """
        :type s: str
        :rtype: bool
        """
        while True:
            l = len(s)
            s = s.replace("()","").replace("[]","").replace("{}","")
            if len(s)==l:
                break
        return len(s)==0
             
```

