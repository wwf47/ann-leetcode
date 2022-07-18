## Problem
Roman to Integer
https://leetcode.cn/problems/roman-to-integer
## Problem Description
```
Roman numerals are represented by seven different symbols: I, V, X, L, C, D and M.
Symbol       Value
I             1
V             5
X             10
L             50
C             100
D             500
M             1000

Example:
Input: s = "III"
Output: 3
Explanation: III = 3.
```

## Code

- Support Language: Python

```
class Solution(object):
    def romanToInt(self, s):
        """
        :type s: str
        :rtype: int
        """
        v = ["M", "a", "D", "b", "C", "c", "L", "d", "X", "e", "V", "f", "I"]
        ll = {"M": 1000, "a": 900, "D": 500, "b": 400, "C": 100, "c": 90, "L": 50, "d": 40, "X": 10, "e": 9, "V": 5, "f": 4, "I": 1}
        s = s.replace("CM", "a")
        s = s.replace("CD", "b")
        s = s.replace("XC", "c")
        s = s.replace("XL", "d")
        s = s.replace("IX", "e")
        s = s.replace("IV", "f")

        res = 0
        for i in range(len(v)):
            while s and s[0] == v[i]:
                s = s[1:]
                res += ll[v[i]]
        return res
```
