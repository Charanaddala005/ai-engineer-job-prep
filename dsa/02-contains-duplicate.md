## pattern:
Sorting technique
Modification of input takes place because the elements in the array will be sorted out

# Contains Duplicate

## Problem

Given an integer array `nums`, return `True` if any value appears
at least twice in the array, and return `False` if every element
is distinct.

## Pattern

Sorting

## My Approach

[Explain your approach in your own words]

## Code

## python
class Solution:
    def hasDuplicate(self, nums: List[int]) -> bool:
        nums.sort()
        n = len(nums)
        for i in range(1, n):
            if nums[i] == nums[i-1]:
                return True
            return False
