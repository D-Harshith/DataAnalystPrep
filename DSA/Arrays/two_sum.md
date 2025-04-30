Problem Name: Two Sum

Problem Number: LeetCode #1

Category: Array, Hash Table

Difficulty: Easy

Problem Description: Given an array of integers and a target sum, return indices of two numbers that add up to the target.

Solution Logic: Use a hash map to store value:index pairs, check for target-num in O(n).

Code Snippet:
```python
def twoSum(nums, target):
    d = defaultdict()
    for i,val in enumerate(nums):
        res = target-val
        if res in d:
            return [d[res], i]
        d[val] = i



Last visited: 4/30/25