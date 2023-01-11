Contains Duplicate
difficulty: easy
language: python

video notes:
 - Methods:
	 - Brute Force -> O(n^2)
	 - Sort -> O(nlogn)
	 - HashSet (uses more mem) -> O(n)
		 - best method

Solution:
```python
class Solution(object):
    def containsDuplicate(self, nums):
        """
        :type nums: List[int]
        :rtype: bool
        """
        hashset = set()

        for n in nums:
            if n in hashset:
                return True
            else:
                hashset.add(n)
        return False
```

Summary:
This helped to reintroduce me to the idea of big O notation and reminded me that memory is also a big factor. Although using a hashset to find duplicates uses the most memory, the time complexity was by far much more quick than brute force (2 loops) or using a sorting algorithm.