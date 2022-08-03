## Problem
Substring with Concatenation of All Words
https://leetcode.cn/problems/substring-with-concatenation-of-all-words/

## Problem Description
```
You are given a string s and an array of strings words of the same length. Return all starting indices of substring(s) in s that is a concatenation of each word in words exactly once, in any order, and without any intervening characters.

Example:
Input: s = "barfoothefoobarman", words = ["foo","bar"]
Output: [0,9]
Explanation: Substrings starting at index 0 and 9 are "barfoo" and "foobar" respectively.
The output order does not matter, returning [9,0] is fine too.

```

## Code

- Support Language: Python

```
class Solution:
    def findSubstring(self, s, words):
        from collections import Counter
        # 处理特殊情况
        return [
            i for i in range(len(s)-len(words)*len(words[0])+1)
            if Counter(
                s[j: j+len(words[0])]
                for j in range(i, i+len(words)*len(words[0]), len(words[0]))
                ) == Counter(words)
        ]
```
