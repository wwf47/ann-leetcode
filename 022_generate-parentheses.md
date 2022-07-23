## Problem
Generate Parentheses
https://leetcode.cn/problems/generate-parentheses/

## Problem Description
```
Given n pairs of parentheses, write a function to generate all combinations of well-formed parentheses.

Example:
Input: n = 3
Output: ["((()))","(()())","(())()","()(())","()()()"]
```

## Code

- Support Language: Python

```
class Solution(object):
    def generateParenthesis(self, n):
        """
        :type n: int
        :rtype: List[str]
        """
        res = []
        def back(S, left, right):
            if len(S)==2*n:
                res.append(''.join(S))
                return
            if left<n:
                S.append('(')
                back(S, left+1, right)
                S.pop()
            if right<left:
                S.append(')')
                back(S, left, right+1)
                S.pop()
        back([], 0, 0)
        return res
```
