Problem Name:  Array Partition

Problem Number: LeetCode #561

Category: Array, Sort

Difficulty: Easy

### New data structure: Counr array/count sort

Problem Description: Given an integer array nums of 2n integers, group these integers into n pairs (a1, b1), (a2, b2), ..., (an, bn) such that the sum of min(ai, bi) for all i is maximized. Return the maximized sum.

Solution Logic: Sort the array and sum the second element in the array.

Code:
```python
def arrayPairSum(self, nums: List[int]) -> int:
    nums.sort()
    ans = 0
    for i in range(0,len(nums), 2):
        ans += nums[i]
    return ans


Last visited: 4/30/25