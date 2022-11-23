
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
## 3. Find All Numbers Disappeared in an Array

Given an array nums of n integers where nums[i] is in the range [1, n], return an array of all the integers in the range [1, n] that do not appear in nums.

```bash
  class Solution:
    def findDisappearedNumbers(self, nums: List[int]) -> List[int]:
        arr=set(nums)
        a,n=[],len(nums)
        for i in range(1,n+1):
            if i not in arr:
                a.append(i)
        return a      
        
```
In order to reduce space consumption, duplicates are removed at first using set() function. 

## 4. Valid Palindrome

Question: Given a string s, return true if it is a palindrome, or false otherwise.

```bash
  class Solution:
    def isPalindrome(self, s: str) -> bool:
        left = 0
        right = len(s)- 1
        while right > left:
            if not s[right].isalnum():
                right = right - 1
                continue
            if not s[left].isalnum():
                left = left + 1
                continue
            if s[left].lower() != s[right].lower():
                return False
            right = right - 1
            left = left + 1
        return True
```        

Start the pointers at two ends and check if the character is alphanumeric. If not, skip a character and then compare it with the other alphanumeric character. 

## 5.  Two Sum

Question: Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

```bash
  class Solution(object):
    def twoSum(self, nums, target):
        length=len(nums)
        for i in range(0,length):
            for j in range(i+1,length):
                num1=nums[i]
                num2=nums[j]
                if num1+num2==target:
                    return [i,j]
```        


