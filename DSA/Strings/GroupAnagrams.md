Problem Name:  Group Anagrams

Problem Number: LeetCode #49

Category: String

Difficulty: Medium

Problem Description: Given an array of strings strs, group the anagrams together. You can return the answer in any order.

Solution Logic: 
* Create a list of 26 length with 0 in it, defaultdict(list).
* For every letter find its position in list and add 1 to that position.
* After iterating through each word add the list as key in dictionary and the actual string as value.

Code:
```python
class Solution:
    def groupAnagrams(self, strs: List[str]) -> List[List[str]]:
        d = defaultdict(list)
        for i in strs:
            abts = [0] * 26
            for j in i:
                idx = ord(j) - ord('a')
                abts[idx] += 1
            d[tuple(abts)].append(i)
        return (list(d.values()))
```
* tuple(abts), because list is mutable and tuple is not which is good option for key.

Last visited: 5/21/25