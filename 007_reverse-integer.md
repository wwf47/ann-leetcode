## Problem
Reverse Integer
https://leetcode.cn/problems/reverse-integer/submissions

## Problem Description
```
Given a signed 32-bit integer x, return x with its digits reversed. If reversing x causes the value to go outside the signed 32-bit integer range [-2**31, 2**31 - 1], then return 0.


Example:
Input: x = 123
Output: 321
```

## Code

- Support Language: Python

```
class Solution(object):
    def reverse(self, x):
        """
        :type x: int
        :rtype: int
        """
        l=1
        INT_MIN, INT_MAX = -2**31, 2**31 - 1
        if x<0:
            l = -1
        x = str(abs(x))[::-1]
        if x< 10:
            return l*x

        r = int(x)
        r = r*l
        if r<INT_MIN or r>INT_MAX:
            return 0
        return r
```
