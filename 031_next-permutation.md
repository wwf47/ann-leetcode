## Problem
Next Permutation
https://leetcode.cn/problems/next-permutation/

## Problem Description
```
A permutation of an array of integers is an arrangement of its members into a sequence or linear order.

For example, for arr = [1,2,3], the following are considered permutations of arr: [1,2,3], [1,3,2], [3,1,2], [2,3,1].
The next permutation of an array of integers is the next lexicographically greater permutation of its integer. More formally, if all the permutations of the array are sorted in one container according to their lexicographical order, then the next permutation of that array is the permutation that follows it in the sorted container. If such arrangement is not possible, the array must be rearranged as the lowest possible order (i.e., sorted in ascending order).

For example, the next permutation of arr = [1,2,3] is [1,3,2].
Similarly, the next permutation of arr = [2,3,1] is [3,1,2].
While the next permutation of arr = [3,2,1] is [1,2,3] because [3,2,1] does not have a lexicographical larger rearrangement.
Given an array of integers nums, find the next permutation of nums.

The replacement must be in place and use only constant extra memory.

```

## Code

- Support Language: Python

```
class Solution(object):
    def nextPermutation(self, nums):
        """
        :type nums: List[int]
        :rtype: None Do not return anything, modify nums in-place instead.
        """
        for i in range(len(nums)-1):
            if nums[-2-i]<nums[-1-i]:
                s = nums[-2-i]
                x = []
                if len(nums)-i-1 == len(nums)-1:
                    nums[-2-i] = nums[-1]
                    nums[-1] = s
                else:
                    for j in range(len(nums)-i-1, len(nums)):
                        print(j)
                        if nums[j] >s:
                            x.append(nums[j])
                    nums[-2-i] = min(x)
                    print(min(x))
                    for j in range(len(nums)-i-1, len(nums)):
                        if nums[j]==nums[-2-i]:
                            nums[j] = s
                            break

                l = nums[-1-i:]
                l.sort()
                nums[-1-i:] = l
                return nums
        return nums.sort()
```
