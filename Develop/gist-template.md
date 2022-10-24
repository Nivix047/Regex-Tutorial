# Title (replace with your title)

Introductory paragraph (replace this with your text)

## Summary

Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

### Anchors

Anchors don't match any characters. What they do is ensure that a regex matches a string at a specific place: the beginning or end of the string or end of a line, or on a word or non-word boundary.

^ - The caret anchor matches the beginning of the text.

Example:

let str = 'JavaScript'; <br/>
console.log(/^J/.test(str)); // expected output: true

$ - The dollar anchor matches the end of the text.

Example:

let str = 'JavaScript'; <br/>
console.log(/t$/.test(str)); // expected output: true

### Quantifiers

Quantifiers indicate numbers of characters or expressions to match.

For example, the regular expression /\4{}4/ matches a four-digit number. It is the same as /\d\d\d\d/:

let str = 'ECMAScript 2020'; <br/>
let re = /\d{4}/;

let result = str.match(re);

console.log(result); // expected output: ["2020"]

### OR Operator

Alternation is the term in regular expression that is actually a simple “OR”. In a regular expression it is denoted with a vertical line character |. For instance, we need to find programming languages: HTML, PHP, Java or JavaScript.

The corresponding regexp: html|php|java(script)?.

A usage example:

let regexp = /html|php|css|java(script)?/gi; <br/>
let str = "First HTML appeared, then CSS, then JavaScript";

console.log( str.match(regexp) ); // expected output: 'HTML', 'CSS', 'JavaScript'

### Character Classes

Character classes distinguish kinds of characters such as, for example, distinguishing between letters and digits.

const chessStory = 'He played the King in a8 and she moved her Queen in c2.'; <br/>
const regexpCoordinates = /\w\d/g;

console.log(chessStory.match(regexpCoordinates)); // expected output: Array [ 'a8', 'c2']

### Flags

A flag is an optional parameter to a regex that modifies its behavior of searching.
There are only 6 of them in JavaScript:

i: With this flag the search is case-insensitive: no difference between A and a.

g: With this flag the search looks for all matches, without it – only the first match is returned.

m: Multiline mode.

s: Enables “dotall” mode, that allows a dot . to match newline character \n.

u: Enables full Unicode support. The flag enables correct processing of surrogate pairs.

y: “Sticky” mode: searching at the exact position in the text (covered in the chapter Sticky flag "y", searching at position).

Example:

let str = "We will, we will rock you";

alert( str.match(/we/gi) ); // expected output: We,we (an array of 2 substrings that match)

### Grouping and Capturing

Capturing groups has two effects:

1. It allows to get a part of the match as a separate item in the result array.
2. If we put a quantifier after the parentheses, it applies to the parentheses as a whole.

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
