# Regex Tutorial

This tutorial is going to go over a very useful regular express (regex) that matches emails: /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/.

## Summary

A regular expression (regex) is a string of text that lets you create patterns that help match, locate, and manage text. In this tutorial, I will be going over the components of a email validating regex.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)

## Regex Components

### **Anchors**

Anchors don't match any characters. What they do is ensure that a regex matches a string at a specific place: the beginning or end of the string or end of a line, or on a word or non-word boundary.

^ - The caret anchor matches the beginning of the text.

Example:

let str = 'test@gmail.com'; <br/>
console.log(/^t/.test(str)); // expected output: true

$ - The dollar anchor matches the end of the text.

Example:

let str = 'test@gmail.com'; <br/>
console.log(/$m/.test(str)); // expected output: true

For email regex, the caret anchor wants the search to return a anything that starts with [a-z0-9_\.-]. The second anchor, the dollar anchor, requires the end of the email to meet the criteria of [a-z\.].

### **Quantifiers**

Quantifiers indicate numbers of characters or expressions to match.

In the regex that matches an email there are two different quantifiers. The "+" character and the a range of {2, 6}. The "+" tells the regex to match everything in the capture group between one and unlimited times. The {2, 6} tells the regex to match everything in the capture group with a character between 2 and 6 times.

### **Character Classes**

Character classes distinguish kinds of characters such as, for example, distinguishing between letters and digits.

For the email regex, there are 3 bracket expressions that have multiple character classes, including two character classes that are matched literally based on the email format ("@" & ".").

- "a-z" for lowercase
- "0-9" for digits
- "\d" for digits
- "\_" and "-" for the characters literally
- "." matches a period literally
- "@" and the external "." for their literal position in the email format

### **Flags**

A flag is an optional parameter to a regex that modifies its behavior of searching.
There are only 6 of them in JavaScript:

i: With this flag the search is case-insensitive: no difference between A and a.

g: With this flag the search looks for all matches, without it – only the first match is returned.

m: Multiline mode.

s: Enables “dotall” mode, that allows a dot . to match newline character \n.

u: Enables full Unicode support. The flag enables correct processing of surrogate pairs.

y: “Sticky” mode: searching at the exact position in the text (covered in the chapter Sticky flag "y", searching at position).

There are no flags to mention for this email regex.

### **Grouping and Capturing**

Group use the () symbol. For the email regex, each character group is in a capture group inside the parenthesis "()".

### **Bracket Expressions**

Brackets indicate a set of characteres to match. Any individual character between the brackets will match, and you can also use a hyphen to define a set.

Example:

'elephant'.match(/[a-d]/) // expected output: matches 'a' <br/>
'elephant'.match(/[A-D]/) // expected output: no match <br/>
'elephant'.match(/[A-D]/i) // expected output: matches 'a' <br/>

The email regex contains three bracket expressions providing three sets of character classes that needs to occur in order for a match to succeed. For example, [a-z0-9_\.-]: this bracket expression states a character may be lowercase letter, a digit between 0 to 9, an underscore, a period, or a hyphen to find a match.

### **Greedy and Lazy Match**

Greedy search - will try to match the longest possible string. Greedy match is marked by the quantifier, "+". Another greedy quantifier in this regex is the {2, 6}, which tells the regex to attempt to match between 2 and 6 times.

Lazy search - will try to match the smallest possible string. Append ? to make the search lazy. For example, ([a-z0-9_\.-]+?) would try to match one or more times, but as few times as possible.

## **Author**

Just a coding enthusiast that wants to share some notes on Regex!

[Github URL](https://github.com/Nivix047)
