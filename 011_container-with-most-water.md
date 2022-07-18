## Problem
Container With Most Water
https://leetcode.cn/problems/container-with-most-water
## Problem Description
```
You are given an integer array height of length n. There are n vertical lines drawn such that the two endpoints of the ith line are (i, 0) and (i, height[i]).

Example:
Input: height = [1,8,6,2,5,4,8,3,7]
Output: 49
Explanation: The above vertical lines are represented by array [1,8,6,2,5,4,8,3,7]. In this case, the max area of water (blue section) the container can contain is 49.
```

## Code

- Support Language: Python

```
class Solution(object):
    def maxArea(self, height):
        """
        :type height: List[int]
        :rtype: int
        """
        l = 0
        r = len(height)-1
        res = 0
        while l<r:
            res = max(res, min(height[l], height[r])*(r-l))
            if height[l]<height[r]:
                l+=1
            else:
                r-=1
        return res
```
