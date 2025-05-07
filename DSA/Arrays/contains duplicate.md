Problem Name: Contains Duplicate

Problem Number: LeetCode #217 

Category: Array

Difficulty: Easy

Problem Description: Given an array of integers and a target sum, return indices of two numbers that add up to the target.

Solution Logic: Use set to eliminate duplicates. Use len() to check lengths.

Code:
```python
def containsDuplicate(self, nums):
    return not len((nums)) == len(set(nums))


Last visited: 5/7/25