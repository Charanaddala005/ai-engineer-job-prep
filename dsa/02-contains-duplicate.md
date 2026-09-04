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

I was given an array of integers and my work is to check if there are any duplicate values present in the given array.
In order to solve this problem i have chosen to use sorting technique by which first and foremost i sort the given array using nums.sort()
then i will have an array of integers with the values going from low to high and if the value of two integers is same then they sit adjacent to each other.
so by checking if the value of two integers is equal that are sitting adjacent to each other i can find out if there are any duplicates present in the array.
that can be achieved by indexes of the sorted array i.e, if nums[i] == nums[i-1] or nums[i] == nums [i+1]
after sorting, equal values are positioned next to each other.

## Code

## python
class Solution:
    def hasDuplicate(self, nums: List[int]) -> bool:
        nums.sort()
TIME COMPLEXITY : O( n logn)
SPACE COMPLEXITY : O(1)
        n = len(nums)
        for i in range(1, n):
            if nums[i] == nums[i-1]:
                return True
            return False
