# Difficulty Level: Easy to Moderate

# Problem Statement:

Valid Parentheses
Given a string s containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

An input string is valid if:

Open brackets must be closed by the same type of brackets.
Open brackets must be closed in the correct order.
Every close bracket has a corresponding open bracket of the same type.
 

Example 1:

Input: s = "()"
Output: true
Example 2:

Input: s = "()[]{}"
Output: true
Example 3:

Input: s = "(]"
Output: false

Constraints:

1 <= s.length <= 104
s consists of parentheses only '()[]{}'.

def isValid(s: str)->bool:
bracket_map={')':'(',']':'[','}':'{'}
stack=[]
for char in s:
if char in bracket_map:
top_element=stack.pop()if stack else'#'
if bracket_map[char] != top_element:
return False 
else:
stack.append(char)
return not stack 

