## Problem
Divide Two Integers
https://leetcode.cn/problems/divide-two-integers/

## Problem Description
```
Given two integers dividend and divisor, divide two integers without using multiplication, division, and mod operator.
The integer division should truncate toward zero, which means losing its fractional part. For example, 8.345 would be truncated to 8, and -2.7335 would be truncated to -2.
Return the quotient after dividing dividend by divisor.

Example:
Input: dividend = 10, divisor = 3
Output: 3
Explanation: 10/3 = 3.33333.. which is truncated to 3.

```

## Code

- Support Language: Python

```
class Solution(object):
    def divide(self, dividend, divisor):
        """
        :type dividend: int
        :type divisor: int
        :rtype: int
        """
        res = 0
        flag = 1
        INT_MIN, INT_MAX = -2**31, 2**31 - 1
        if dividend<0 and divisor<0:
            flag = 1
        elif dividend<0 or divisor<0:
            flag = -1
        else:
            flag = 1
        end = abs(dividend)
        sor = abs(divisor)
        while end >= sor:
            i = 1
            tmp = sor
            while tmp<=end:
                end = end - tmp
                res += i
                i = i<<1
                tmp = tmp<<1
        if flag==-1:
            res = 0-res
        if res> INT_MAX or res<INT_MIN:
            res = INT_MAX
        return res
```
