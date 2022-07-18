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
        
        for i in range(1, len(strs)):
            while mid not in strs[i]:
                mid = mid[:-1]

        for i in range(1, len(strs)):
            for j in range(len(mid)):
                if mid[j]!=strs[i][j]:
                    mid = mid[:j]
                    break
        res = mid 
        return res
```
