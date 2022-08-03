## Problem
Search Insert Position
https://leetcode.cn/problems/search-insert-position/

## Problem Description
```
Given a sorted array of distinct integers and a target value, return the index if the target is found. If not, return the index where it would be if it were inserted in order.
You must write an algorithm with O(log n) runtime complexity.

Example:
Input: nums = [1,3,5,6], target = 5
Output: 2
```

## Code

- Support Language: Python

```
class Solution(object):
    def searchInsert(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: int
        """
        if target in nums:
            return nums.index(target)
        
        l = 0
        while l<len(nums):
            if nums[l]>target:
                return l
            else:
                l+=1
        return l
```
