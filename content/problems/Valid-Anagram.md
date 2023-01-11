Valid Anagram
difficulty: easy
language: python

video notes:
- anagram is a word that uses the same exact letters as another word
- check word lengths first
- hashmap makes most sense
- O(S+T) --> S and T are the unique words

solution:
```python
class Solution(object):
    def isAnagram(self, s, t):
        if (len(s) != len(t)):
            return False
        sHash, tHash = {}, {}

        for i in range(len(s)):
            sHash[s[i]] = 1 + sHash.get(s[i], 0)
            tHash[t[i]] = 1 + tHash.get(t[i], 0)

        for k in sHash:
            if sHash[k] != tHash.get(k, 0):
                return False
        
        return True
```


summary:
This problem takes a few more lines of code, but one interesting thing to point out is that on the last non-return line we had to use the get() method instead of checking the key of the 'tHash' hashmap because if that key did not exist in that hashmap it would throw an error. The get() method is very important to know because you can set that default return value.
