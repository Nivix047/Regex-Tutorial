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

Example:

alert( 'Gogogo now!'.match(/(go)+/ig) ); // expected output: "Gogogo"

### Bracket Expressions

Brackets indicate a set of characteres to match. Any individual character between the brackets will match, and you can also use a hyphen to define a set.

Example:

'elephant'.match(/[a-d]/) // expected output: matches 'a' <br/>
'elephant'.match(/[A-D]/) // expected output: no match <br/>
'elephant'.match(/[A-D]/i) // expected output: matches 'a' <br/>

### Greedy and Lazy Match

Greedy search - will try to match teh longest possible string.

Example:

const str = `<div> <h1>Hello World</h1> </div?`; <br/>
const greedyRE = /<. + >/g

str.match(greedyRE) // expected output: `[ '<div>', '<h1>Hello World</h1>', '</div>' ]`

Lazy search - will try to match the smallest possible string. Append ? to make the search lazy.

Example:

const str = `<div> <h1>Hello World</h1> </div?`; <br/>
const lazyRE = /<. +? >/g

str.match(lazyRE) // expected output: `[ '<div>', '<h1>', '</h1>', '</div>' ]`

### Boundaries

When the regexp engine (program module that implements searching for regexps) comes across \b, it checks that the position in the string is a word boundary.

Example:

alert( "Hello, Java!".match(/\bJava\b/) ); // expected output: Java <br/>
alert( "Hello, JavaScript!".match(/\bJava\b/) ); // expected output: null

### Back-references

A group can be referenced in the pattern using \N, where N is the group number. <br/>

To make clear why that’s helpful, let’s consider a task. <br/>

We need to find quoted strings: either single-quoted '...' or a double-quoted "..." – both variants should match. <br/>

How to find them? <br/>

We can put both kinds of quotes in the square brackets: `['"](.*?)['"]`, but it would find strings with mixed quotes, like "...' and '...". That would lead to incorrect matches when one quote appears inside other ones, like in the string "She's the one!":

let str = `He said: "She's the one!".`;

let regexp = /(['"])(.\*?)\1/g;

alert( str.match(regexp) ); // expected output: "She's the one!"

### Look-ahead and Look-behind

It's used to find only those matches for a pattern that are followed or preceded by another pattern.

Lookahead

The syntax is: X(?=Y), it means "look for X, but match only if followed by Y". There may be any pattern instead of X and Y.

Example:

For an integer number followed by €, the regexp will be \d+(?=€):

let str = "1 turkey costs 30€";

alert( str.match(/\d+(?=€)/) ); // expected output: 30, the number 1 is ignored, as it's not followed by €

Lookbehind

Lookbehind is similar, but it looks behind. That is, it allows to match a pattern only if there’s something before it.

Example:

The dollar sign is usually before the number, so to look for `$30` we’ll use (?<=\$)\d+ – an amount preceded by $:

let str = "1 turkey costs $30";

alert( str.match(/(?<=\$)\d+/) ); // expected output: 30 (skipped the sole number)

## Author

Daniel is a coding enthusiast that wants to share some notes on Regex!

[Github URL](https://github.com/Nivix047)

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
