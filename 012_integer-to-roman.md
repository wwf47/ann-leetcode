## Problem
Integer to Roman
https://leetcode.cn/problems/integer-to-roman

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
Input: num = 3
Output: "III"
Explanation: 3 is represented as 3 ones.
```

## Code

- Support Language: Python

```
class Solution(object):
    def intToRoman(self, num):
        """
        :type num: int
        :rtype: str
        """
        v = [1000, 900, 500, 400, 100, 90, 50, 40, 10, 9, 5, 4, 1]
        ll = {1000: "M", 900: "CM", 500: "D", 400: "CD", 100: "C", 90: "XC", 50: "L", 
        40: "XL", 10: "X", 9: "IX", 5: "V", 4: "IV", 1: "I"}
        res = ''      
        for i in range(len(ll)):
            while num>=v[i]:
                num = num-v[i]
                res += ll[v[i]]
        return res
```
