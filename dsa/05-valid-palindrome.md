python code:
class Solution:
    def isPalindrome(self, s: str) -> bool:
        s = s.lower()

        i = 0
        j = len(s) - 1

        while i < j:

            while i < j and not s[i].isalnum():
                i += 1
            while i < j and not s[j].isalnum():
                j -= 1
            if s[i] != s[j]:
                return False

            i += 1
            j -= 1

        return True
algorithm:
initaily we have to lower the cases of teh given string of characters beacuse the question is case sensitive and this helps in keeping all  the characters same
now we consider two pointers i and j and i starts from the beginning of the string and j starts from the last character of the string.
now comes the condition if i pointer is located before j and character in the i is not alnum() i.e, alphanumerical then we proceed the i to +i,
similarly if the j pointer is ahead of i and character in j is not alnum() then we move j pointer to backward from j to -j
we use precondition check such that if the characters are not same it is not considered as a palindrome.
and while condition runs code as the condition stays true
