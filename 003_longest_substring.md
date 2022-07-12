## Problem
Longest Substring Without Repeating Characters
https://leetcode.cn/problems/longest-substring-without-repeating-characters

## Problem Description
```
Given a string s, find the length of the longest substring without repeating characters.

Example:
Input: s = "abcabcbb"
Output: 3
Explanation: The answer is "abc", with the length of 3.
```

## Code

- Support Language: Python

```
class Solution(object):
    def lengthOfLongestSubstring(self, s):
        """
        :type s: str
        :rtype: int
        """
        if len(s)==0:
            return 0
        maxlen = 0
        for i in range(len(s)):
            maxs = ''
            for j in range(i, len(s)):
                if s[j] not in maxs:
                    maxs = s[i:j+1]
                    if maxlen<len(maxs):
                        maxlen = len(maxs)
                else:
                    break
        return maxlen
```
