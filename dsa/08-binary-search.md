python code:
class Solution:
    def search(self, nums: List[int], target: int) -> int:

        left = 0
        right = len(nums) - 1  
        

        while left <= right:
            mid = (left + right) // 2

            if nums[mid] == target:
                return mid

            if nums[mid] < target:
                left = mid + 1

            if nums[mid] > target:
                right = mid - 1

        return -1
algorithm :
so in this binary search we were already given the sorted array so we have the elements in ascending order
no we use left, right and mid concept 
initially left pointer is at the beginning and right pointer will be at the end of an array
now using while condition if left<= right and mid is at the center of the array i.e, (left + right)//2
we check if the center == target and return number located at the mid if it matches with the target
if that number is to the left of the target then we shift out pointer to the adjacent number of the mid and vice versa.
