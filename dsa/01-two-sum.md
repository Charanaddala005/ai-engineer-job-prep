# Two Sum

## Problem

Given an array of integers `nums` and an integer `target`,
return the indices of the two numbers that add up to `target`.

## Pattern

Hash Map

## My Approach

Brute force approach was used where i and j as two different variables assigned to the integers in the array.
firsty 'i' will be given amomg the integers and 'j' is assigned to other integer rather than 'i' because same value cannot be assigned to both the variables.
Now we use if nums[i] + nums[j] == target , return [i,j] this will check for the possible values of i and j so that we can get the target value.
Also i and j are said to be given different values so the range of i varies from (0,n) whereas range of j varies from (i+1 , n).

## Code

class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
    n = len(nums)
    for i in range(0,n):
       for j in range(i+1,n):
            if nums[i] + nums[j] == target:
                 return [i,j]
    return 0

  Different approach using hash map:

Step 1:
Create an empty hash map to store each number and its index.

Step 2:
Traverse the array from left to right.

Step 3:
For the current number, calculate its complement:

complement = target - current number

Step 4:
Check whether the complement already exists in the hash map.

Step 5:
If the complement exists, return:
[index of complement, current index]

Step 6:
If the complement does not exist, store the current
number and its index in the hash map.

Step 7:
Continue until the required pair is found.

## Python code
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        n = len(nums)
        hashMap = {}
        for i in range(0,n):
             diff = target - nums[i]
             if diff in hashMap:
                return [hashMap[diff], i]
             hashMap[nums[i]] = i
TIME COMPLEXITY : O(n)
SPACE COMPLEXITY : O(n)

  
    
