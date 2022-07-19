## Problem
3Sum Closest
https://leetcode.cn/problems/3sum-closest

## Problem Description
```
Given an integer array nums of length n and an integer target, find three integers in nums such that the sum is closest to target.

Example:
Input: nums = [-1,2,1,-4], target = 1
Output: 2
Explanation: The sum that is closest to the target is 2. (-1 + 2 + 1 = 2).
```

## Code

- Support Language: Python

```
class Solution(object):
    def threeSumClosest(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: int
        """
        mins = 100000
        res = 0
        nums.sort()
        for i in range(len(nums)):
            l = i+1
            r = len(nums)-1
            while l<r :
                if abs(nums[i]+nums[l]+nums[r]-target)<mins:
                    mins = abs(nums[i]+nums[l]+nums[r]-target)
                    res = nums[i]+nums[l]+nums[r]
                if nums[i]+nums[l]+nums[r]>target:
                    r-=1
                elif nums[i]+nums[l]+nums[r]==target:
                    return target
                else:
                    l+=1
        return res
```
