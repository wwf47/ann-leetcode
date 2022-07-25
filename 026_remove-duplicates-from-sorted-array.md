## Problem
Remove Duplicates from Sorted Array
https://leetcode.cn/problems/remove-duplicates-from-sorted-array/

## Problem Description
```
Given an integer array nums sorted in non-decreasing order, remove the duplicates in-place such that each unique element appears only once. The relative order of the elements should be kept the same.
Since it is impossible to change the length of the array in some languages, you must instead have the result be placed in the first part of the array nums. More formally, if there are k elements after removing the duplicates, then the first k elements of nums should hold the final result. It does not matter what you leave beyond the first k elements.
Return k after placing the final result in the first k slots of nums.

Example:
Input: nums = [1,1,2]
Output: 2, nums = [1,2,_]
Explanation: Your function should return k = 2, with the first two elements of nums being 1 and 2 respectively.
It does not matter what you leave beyond the returned k (hence they are underscores).

```

## Code

- Support Language: Python

```
class Solution(object):
    def removeDuplicates(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        k = 0
        while k<len(nums)-1:
            if nums[k]==nums[k+1]:
                del nums[k+1]
            if k<len(nums)-1 and nums[k]!=nums[k+1]:
                k += 1
        return len(nums)
```
