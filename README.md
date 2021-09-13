# Powerful Password Matcher

Welcome to Powerful Password Matcher!!
I will be using a regex, short for regular expression, in order to validate a unique and powerful password.   
A regex is a string of text that allows one to create a pattern that assists in matching, locating and managing text.  
In order to test your passwords validity, copy the regex code and paste it in a regex tester (eg: https://regexr.com/) then enter your chosen password.  
If your password meets the criteria you will be certain to have a great password!   
Be creative but don't forget to create something you can easily remember!!  

## Summary

The regex I am describing is for creating and validating a strong password by meeting the following criteria
- must include at least 8 and up to 20 characters
- must include at least one upper case letter
- must include at least one lower case letter
- must include at least one digit
- must include at least one special character


## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Lazy Match](#lazy-match)
- [Look-ahead and Look-behind](#look-ahead-and-Look-behind)
- [Examples of Password Checks](#examples-of-password-checks)
- [Author](#author)

## Regex Components
`/^(?=.*?[A-Z])(?=.*?[a-z])(?=.*?[0-9])(?=.*?[#?!@$ %^&*-:()]).{8,20}$/`   

Simple Explanation of the regex  
`/`Beginning of the paragraph   
`^`Beginning of the string  
`(?=.*?[A-Z])`Look-ahead and assess for at least one upper case character   
`(?=.*?[a-z)`Look-ahead and assess for at least one lower case character    
`(?=.*?[0-9])`Look-ahead and assess for at least one digit  
`(?=.*?[#?!@$ %^&*-:()])` Look-ahead and assess for at least one special character  
`.`Matches any character  
`{8,21}`Ensure the password is a minimum of 8 and a maximum of 20 characters long  
`$`End of the string  
`/`End of the paragraph

### Anchors
An Anchor is a token that does not match any character but rather matches a particular position within the regex.  
`/` When this is at the beginnning of the paragraph it denotes the beginning of a regular expression paragraph,   
    when at the end of the paragraph it denotes the end.  

`^` This denotes the beginning of the string or the line of a mulitline flag if enabled, this matches a position and not a character in the paragraph.


`$` This denotes the end of the string or the end of the line if a multiline flag is enabled.  

### Quantifiers
Quantifier originates from the latin quantas meaning how much/how often. In regex it indicates the number of characters or expressions required to match the required input.  
`*` Assesses the preceding tokens to match 0 or more of the criteria.   
`(?=.*?[A-Z])` in this snippet of code the `*` is letting us assess if any upper case letters have been entered.   
`{}` Matches the number of characters in the preceding tokens necessary to validate the input data.  
`{8,20}` In this snippet the quantifier is stating there must be a minimum of 8 characters and a maximum of 21 characters for the password to be validated.    

### Character Classes
Character classes refer to the set of characters which can occur in an input string in order for a match to succeed.  
Examples and snippets of Character classes from my regex are as follows:  
`[]` Are used to define a character class.    
`.` Matches any single character except a new line.    
`[A-Z]` Matches upper case letters.    
`[a-z]` Matches lower case letters.    
`[0-9]` Matches digits between 0 and 9.    
`[#?!@$ %^&*-]` Matches the listed special characters.    

### Grouping and Capturing
Grouping and capturing refers to the section of the regular expression enclosed in parentheses. It allows each group to either match, fail or repeat the input data.    
`()` Parentheses are used to place a particular part of a regex so they can group that part of the regex together,   
   this also captures the information within the parentheses.  
`(?=.*?[0-9])` This snippet describes the requirement of entering at least one digit and assessing whether or not a digit has been entered.  

### Bracket Expressions
`{}` Are used to specify the exact amount of things to match.    
`[]` Are used to define a character class.   
`()` Parentheses are used to place a particular part of a regex in order so they can group that part of the regex together,   
   this also captures the information within the parentheses.   
`(?=.*?[#?!@$ %^&*-:()]).{8,20}` If we break down this snippet we can see that the curly braces enclose the required minimum and maximum length of the password,  
    the square braces enclose the list of characters that are allowed, in  this case the list is of special characters, and the parentheses enclose  
    the entire definition of that particular grouping.

### Lazy Match
Lazy match is defined as finding as few matches as possible. The opposte of lazy match is greedy which is defined as eating up as many tokens as possible.  
`?` Denotes the lazy match allowing the preceding quantifier to match as few characters as possible.   
`*?` In this snippet the lazy match is referring to the `*` quantifier which is searching for 0 or more matches.  

### Look-ahead and Look-behind
`(?=)` This refers to Look-ahead and allows a search for the character or characters in that particular group or class,   
       if the character is present then the regex recognizes the match and if it is not it rejects it.  
 `(?=.*?[a-z])` This snippet is Looking-ahead in order to determine if any lower case characters have been entered in order to pass the validation.  
 `(?<=)` This refers to Look-behind and assesses the input already entered. This could also be used, however it is not recognized in all languages so it has been not included it in my regex.  

## Examples of Password Checks
Pass: iLuvCh0c0latEcake:)!!  
_contains 8 to 20 characters ✓_   
_contains at least one upper case letter ✓_    
_contains at least one lower case letter ✓_    
_contains at least one digit ✓_   
_contains at least one special character ✓_   

Fail: idontlUvChOcOlatEcake:(!!  
_contains 8 to 20 characters ✗_   
_contains at least one upper case letter ✓_   
_contains at least one lower case letter ✓_   
_contains at least one digit ✗_   
_contains at least one special character ✓_   

## Author
Created by Kristen Groller  
I am presently enrolled in the U of T Coding bootcamp.   
I hope this gist helps you validate a powerful password.  
Github link https://github.com/Kgroll  
