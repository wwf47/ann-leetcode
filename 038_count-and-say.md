## Problem
Count and Say
https://leetcode.cn/problems/count-and-say/

## Problem Description
```
The count-and-say sequence is a sequence of digit strings defined by the recursive formula:
countAndSay(1) = "1"
countAndSay(n) is the way you would "say" the digit string from countAndSay(n-1), which is then converted into a different digit string.
To determine how you "say" a digit string, split it into the minimal number of substrings such that each substring contains exactly one unique digit. Then for each substring, say the number of digits, then say the digit. Finally, concatenate every said digit.

For example, the saying and conversion for digit string "3322251":
```

## Code

- Support Language: Python

```
class Solution(object):
    def countAndSay(self, n):
        """
        :type n: int
        :rtype: str
        """
        if n == 1:
            return "1"
        else:
            s = self.countAndSay(n-1)
            i,j = "1", 0
            res = ""
            l = 0
            while l<len(s)-1:
                if s[l]!=s[l+1]:
                    i = s[l]
                    j+=1
                    res += str(j)+str(i)
                    j = 0
                else:
                    i = s[l]
                    j+=1
                l+=1
            if s[l]!=s[l-1]:
                res+= "1"+str(s[l])
            else:
                res+=str(j+1)+str(s[l])
        return res
```
