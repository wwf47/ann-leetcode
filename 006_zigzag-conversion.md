## Problem
ZigZag Conversion
https://leetcode.cn/problems/zigzag-conversion

## Problem Description
```
The string "PAYPALISHIRING" is written in a zigzag pattern on a given number of rows like this: (you may want to display this pattern in a fixed font for better legibility)

P   A   H   N
A P L S I I G
Y   I   R

And then read line by line: "PAHNAPLSIIGYIR"

Write the code that will take a string and make this conversion given a number of rows:

Example:
Input: s = "PAYPALISHIRING", numRows = 3
Output: "PAHNAPLSIIGYIR"
```

## Code

- Support Language: Python

```
class Solution(object):
    def convert(self, s, numRows):
        """
        :type s: str
        :type numRows: int
        :rtype: str
        """
        if numRows==1 or numRows>=len(s):
            return s
        n = len(s)

        t = numRows*2-2
        if n%t<=numRows:
            c = n//t*(numRows-1)+1
        elif n%t>numRows:
            c = n//t*(numRows-1)+n%t-numRows+1
        else:
            c = n//t*(numRows-1)
        mat = [['']*c for _ in range(numRows)]

        x,y = 0,0

        for i, v in enumerate(s):
            mat[x][y] = v
            if i%t < numRows-1:
                x +=1
            else:
                x -=1
                y+=1
        
        r = ''
        for j in range(numRows):
            for k in range(c):
                r +=mat[j][k]
        return r
```
