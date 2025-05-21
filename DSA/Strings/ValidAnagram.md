Problem Name:  Valid Anagram

Problem Number: LeetCode #242

Category: String

Difficulty: Easy

Problem Description: Given two strings s and t, return true if t is an anagram of s, and false otherwise.

Solution Logic: 
* Create a list of 26 length with 0 in it.
* Iterate through s, find index of every element using ord(i)-ord('a') and increase the index in list by 1.
* Now, iterate through t, find index of every element using ord(i)-ord('a') and decrease the index in list by 1.4
* In the end, iterte through list if any value is not 0 then strings are not anagram.

Code:
```python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        abt = [0] * 26
        for i in s:
            abt[ord(i) - ord('a')] += 1
        for i in t:
            abt[ord(i) - ord('a')] -= 1
        for i in abt:
            if i != 0:
                return False
        return True
```

Last visited: 5/21/25