pyhton code:
class Solution:
    def isValid(self, s: str) -> bool:
        stack = []

        mapping = {
            ")": "(",
            "]": "[",
            "}": "{"
        }

        for c in s:

            if c in mapping:

                if not stack:
                    return False

                if stack[-1] != mapping[c]:
                    return False

                stack.pop()

            else:
                stack.append(c)

        return not stack
algortihm:
we use mapping to solve the problem and also uses stack 
so we initially map the values of parantheses accordingly
we use a pointer named c in the stack and check if the character we chose is in the stack 
before that we check if the stack is empty or not 
then we check for the top most element using stack[-1] !
if the top most element matches with the mapping element of the 'c' then we append the element to the stack.
or else we pop the element present in the stack
