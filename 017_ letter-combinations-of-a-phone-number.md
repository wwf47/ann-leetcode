## Problem
Letter Combinations of a Phone Number
https://leetcode.cn/problems/two-sum

## Problem Description
```
Given a string containing digits from 2-9 inclusive, return all possible letter combinations that the number could represent. Return the answer in any order.
A mapping of digits to letters (just like on the telephone buttons) is given below. Note that 1 does not map to any letters.

Example:
Input: digits = "23"
Output: ["ad","ae","af","bd","be","bf","cd","ce","cf"]
```

## Code

- Support Language: Python

```
class Solution(object):
    def letterCombinations(self, digits):
        """
        :type digits: str
        :rtype: List[str]
        """
        if len(digits)==0:
            return []
        
        l = {"2": ["a", "b", "c"], "3": ["d", "e", "f"], "4": ["g", "h", "i"], 
        "5": ["j", "k", "l"], "6":["m", "n", "o"], "7": ["p","q", "r", "s"], 
        "8": ["t","u","v"], "9": ["w","x","y","z"]}
        res = [""]

        for i in digits:
            res = [s+m for m in l[i] for s in res]
        return res
```