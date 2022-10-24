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

console.log(result); // expect output: ["2020"]

### OR Operator

### Character Classes

### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
