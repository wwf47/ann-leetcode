## Problem
String to Integer
https://leetcode.cn/problems/two-sum

## Problem Description
```
Implement the myAtoi(string s) function, which converts a string to a 32-bit signed integer (similar to C/C++'s atoi function).

Example:
Input: s = "42"
Output: 42
Explanation: The underlined characters are what is read in, the caret is the current reader position.
Step 1: "42" (no characters read because there is no leading whitespace)
         ^
Step 2: "42" (no characters read because there is neither a '-' nor '+')
         ^
Step 3: "42" ("42" is read in)
           ^
The parsed integer is 42.
Since 42 is in the range [-231, 231 - 1], the final result is 42.

```

## Code

- Support Language: Python

```
class Solution(object):
    def myAtoi(self, s):
        """
        :type s: str
        :rtype: int
        """
        INT_MIN, INT_MAX = -2**31, 2**31 - 1
        s = s.strip()        
        r = 0
        l=1
        if len(s) == 0:
            return 0
        if len(s) == 0:
            return 0
        if s[0] == '-':
            l = -1
            s = s[1:]
        elif s[0] == '+':
            s = s[1:]
        else:
            pass
        if len(s) == 0:
            return 0
        if s[0]<'0' or s[0]>'9':
            return 0
        
        ss = ''
        for i in range(len(s)):
            if s[i]>='0' and s[i]<='9':
                ss += s[i]
            else:
                break

        r = int(ss)
        r = r*l
        print(r)
        if r<INT_MIN:
            r = INT_MIN
        if r>INT_MAX:
            r = INT_MAX
        return r
```
