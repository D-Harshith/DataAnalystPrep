Problem Name: Move Zeros
Problem Number: LeetCode #283

Category: Array, Two pointer

Difficulty: Easy

Problem Description: Given an integer array nums, move all 0's to the end of it while maintaining the relative order of the non-zero elements.

Solution Logic: Get all the non zero values to left.
* Start from the zero index. Initiate 2 pointers left, right. If right value is != 0 then swap with the left value and increment left value by 1 position.

Code:
```python
def moveZeroes(self, nums: List[int]) -> None:
    left = 0
    for right in range(len(nums)):
        if nums[right] != 0:
            nums[left], nums[right] = nums[right], nums[left]
            left += 1
            
Last visited: 5/7/25