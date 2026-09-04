Method 1: (sorting technique)

Given two strings s and t, return true if the two strings are anagrams of each other, otherwise return false.
Two strings are anagrams if they contain the same characters, with each character appearing the same number of times, regardless of order.

Algorithm:
step1 : immediately after looking sentence regardless the order the first thing that came up to my mind for sorting technique
step2 : all did was assigned new value after sorting both of the strings
step3 : check if both the sorted strings have equal values or not 

Python code: 
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
       s1 = sorted(s)
       t1 = sorted(t)
       if s1 == t1:
           return True
        return False

 Method 2 : (hash map)

Algorithm :
step1 : i have assigned new values to the lengths of both the strings
step2 : also i have kept an early check such that if the lengths of the given strings is not equal then they are no way to be anagrams
step3 : now i have created hashmaps for both the strings to store the count of the characters in the string
step4 : now for each string i have to add +1 if the character is repeated and have to assign 1 if the character is entered new
step5 : same way was done to the other string of characters
step6 : now we have count of each characters in the both strings all we have to do is compare them.

Python code:
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
           m = len(s)
        n = len(t)
        if m != n:
            return False
        count_s = {}
        count_t = {}
        for i in range(0,m):
            if s[i] in count_s:
                count_s[s[i]] = count_s[s[i]] + 1
            else:
                count_s[s[i]] = 1
        for j in range(0,n):
            if t[j] in count_t:
                count_t[t[j]] = count_t[t[j]] + 1
            else:
                count_t[t[j]] = 1
        if count_s == count_t:
            return True
        return False
          


       
