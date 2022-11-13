
# List of Leetcode Problems that I adore

A brief description of what this project does and who it's for


## 1. Contains Duplicate

I originally solved the problem like this:

```bash
  class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        dict_nums = {}

        for i in nums:
            if i in dict_nums:
                return True
            else:
                dict_nums[i] = 1
        
        return False
```
It did work but when I looked at the discussions section, I found this incredibly sexy solution.
🥵
```bash
  def containsDuplicate(nums):
	return len(set(nums)) != len(nums)
```

## 2. Missing Number

Question: Given an array nums containing n distinct numbers in the range [0, n], return the only number in the range that is missing from the array.

```bash
  class Solution:
    def missingNumber(self, nums: List[int]) -> int:
        
        l=len(nums)+1
        for i in range(l):
            if(i not in nums):
                return i
        return 0 
       
        
```
