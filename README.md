
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

## 6.   Palindrome Number

Question: Given an integer x, return true if x is a palindrome, and false otherwise.

```bash
  class Solution:
    def isPalindrome(self, x: int) -> bool:
        if x < 0:
            return False
        else:
            a = x
            c = 0
            while x != 0:
                c = c*10 + x%10
                x = x//10
            if a == c:
                return True
            else:
                return False
```        
## 7.   Valid Anagram

Question: Given two strings s and t, return true if t is an anagram of s, and false otherwise.

```bash
  class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        a= sorted([x for x in s])
        b = sorted([y for y in t])
        if len(a) == len(b):
            if a==b:
                return True
            else: 
                return False
        return False
```        
## 8.   Valid Parenthesis

Question: Given a string s containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

```bash
  class Solution:
    def isValid(self, s: str) -> bool:
        stack = []
        brackets = {
            ")" : "(",
            "}" : "{",
            "]" : "["            
        }
        
        for char in s:
            if char in brackets:
                if stack and stack[-1] == brackets[char]:
                    stack.pop()
                else:
                    return False
            else:
                stack.append(char)
        return True if not stack else False
        

```        
## 9.   Matrix Diagonal Sum

Question: Given a square matrix mat, return the sum of the matrix diagonals. Only include the sum of all the elements on the primary diagonal and all the elements on the secondary diagonal that are not part of the primary diagonal.

```bash
  class Solution(object):
    def diagonalSum(self, mat):      
        total_sum = 0     
        
        for i in range(len(mat)):
            
            for j in range(len(mat)):
                
                if i == j:
                    total_sum += mat[i][j]
                
        i = 0
        
        for j in range(len(mat)-1,-1,-1):
                
            if i == j:
                pass

            else:
                total_sum += mat[i][j]

            i += 1
                
        return total_sum
```        
## 10.   Roman to Integer

Question: Given a roman numeral, convert it to an integer.

```bash
  class Solution:
    def romanToInt(self, s: str) -> int:
        roman_integers = {
            "I": 1,
            "V": 5,
            "X": 10,
            "L": 50,
            "C": 100,
            "D": 500,
            "M": 1000
        }
        total = 0
        
        for i in range(1,len(s)):
            if roman_integers[s[i-1]] < roman_integers[s[i]]:
                total = total - roman_integers[s[i-1]]
            else:
                total = total + roman_integers[s[i-1]]
        
        return total+roman_integers[s[-1]]
            
```        


