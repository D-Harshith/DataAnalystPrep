Problem Name:  Longest Substring Without Repeating Characters

Problem Number: LeetCode #3

Category: String, Sliding window

Difficulty: Medium

Problem Description: Given a string s, find the length of the longest substring without duplicate characters.

Solution Logic: 
* We will go letter by letter and keep track of what we have seen so far. If we see a repeating character, we remove letters from the beginning until there's no repetition.

* We start with index 0(start = 0) and we add the value as key to dictionary with its index as value. When we find a repeting character we move the start to right by 1 index. 

* We record the max length in each step with max(max_len, end - start + 1) 

Code:
```python
class Solution(object):
    def lengthOfLongestSubstring(self, s):
        char_index = {}
        max_len = 0
        start = 0

        for end in range(len(s)):
            if s[end] in char_index and char_index[s[end]] >= start:
                start = char_index[s[end]] + 1
            char_index[s[end]] = end
            max_len = max(max_len, end-start+1)
        return max_len
```
* char_index[s[end]] >= start: This condistion to check the repeating character in the window currently we are in. Not from the beginning.

Ex: Input: "abba"

'a' at index 0 → no issue

'b' at index 1 → no issue

'b' at index 2 → duplicate! Last seen at 1, and start = 0 → move start = 2

'a' at index 3 → 'a' was seen at 0 but that’s before start = 2 → not in window → OK

Last visited: 5/21/25