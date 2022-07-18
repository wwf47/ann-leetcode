## Problem
Longest Common Prefix
https://leetcode.cn/problems/longest-common-prefix

## Problem Description
```
Write a function to find the longest common prefix string amongst an array of strings.
If there is no common prefix, return an empty string "".

Example:
Input: strs = ["flower","flow","flight"]
Output: "fl"
```

## Code

- Support Language: Python

```
class Solution(object):
    def longestCommonPrefix(self, strs):
        """
        :type strs: List[str]
        :rtype: str
        """
        res = ""
        mid = strs[0]

        for i in range(len(mid)):
            l = 0 
            for j in range(1, len(strs)):
                if i>len(strs[j])-1:
                    l = 1
                    break
                elif mid[i]!=strs[j][i]:
                    l = 1
                    break
            if l == 0:
                res += mid[i]
            else:
                break
        return res
```
