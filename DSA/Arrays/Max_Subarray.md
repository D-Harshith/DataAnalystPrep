Problem Name: Maximum subarray

Problem Number: LeetCode #53

Category: Array

Difficulty: Easy

Problem Description: Given an array return the maximum sum of the subarray.

Solution Logic: Take the first element as the total sum and initialize a result variable=0, add the elements one by one to total. If total<0 then make total=0 and update the res with max(res, total).

Code:
```python
def maxSubArray(self, nums: List[int]) -> int:
    res = nums[0]
    total = 0
    for n in nums:
        if total < 0:
            total = 0
        total += n
        res = max(res, total)
    return res

Last visited: 5/7/25