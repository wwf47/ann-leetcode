## Problem
Find First and Last Position of Element in Sorted Array
https://leetcode.cn/problems/find-first-and-last-position-of-element-in-sorted-array/

## Problem Description
```
Given an array of integers nums sorted in non-decreasing order, find the starting and ending position of a given target value.
If target is not found in the array, return [-1, -1].
You must write an algorithm with O(log n) runtime complexity.

Example:
Input: nums = [5,7,7,8,8,10], target = 8
Output: [3,4]
```

## Code

- Support Language: Python

```
class Solution(object):
    def searchRange(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        res = []
        if target in nums:
            res.append(nums.index(target))
            rev = nums[::-1]
            res.append(len(nums)-rev.index(target)-1)
        else:
            res = [-1, -1]
        return res
```
