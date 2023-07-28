# Regex Tutorial

Regex (or regular expression) is used to search for a specific pattern among a body of text. It may look cryptic, but once broken down, you will realize how simple each part of it really is.

## Summary

Regex uses a combination of strategies to define patterns. Characters left on their own mean themselves - for example, ```cake``` would represent the word 'cake'. Meta characters involve backslashes in front of a character, and represent a group of characters. For example, ```\d``` represents any digit 0 through 9. Regex phrases will be inside ```/``` characters because it is a literal. Each section of this tutorial will address one component of regex.

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
There are 2 examples of anchors in regex:
- ```^```
- ```&```
The ```^``` character means that the pattern starts with whatever follows it. For example, ```^cake``` would look for a pattern starting with 'cake'. The ```&``` character works the same way, but instead mean that the pattern ends with the previous characters. This will become much more useful when combined with other components.

### Quantifiers
Quantifiers specify how many of a pattern to look for:
- ```*``` means 0 or more times
- ```+``` means 1 or more times
- ```?``` means 0 or 1 time.
Curly brackets do the same but are more specific:
- ```{ x }``` means exactly x number of times
- ```{ x, }``` means at least x number of times
- ```{ x, y }``` means from x to y number of times
An example looking for a password inbetween 8 and 32 characters looks like this: ```/^{8,32}$/```.

### OR Operator
The or operator uses the ```|``` character, and is fairly self explanatory. In this example, it will look for anything that matches either 'a', 's', or 'd': ```/(a|s|d)/```.

### Character Classes
These represent groups of characters:
- ```.``` means any character except ```\n``` (new line)
- ```\d``` means digits 0 through 9
- ```\c``` means an uppercase or lowercase letter
- ```\w``` means characters from the Latin alphabet (including '_')
- ```\s``` means a whitespace character (spaces, tabs, line breaks, etc.)
Any of these can be used in exclusion rather than inclusion. For example, ```\W``` would look for anything not included in the Latin alphabet.

### Flags
These are put at the end of the second slash, and act as rules for filtering.
- ```g``` (global) means the regex and search without limitations
- ```i``` (case insensitive) means case has to be ignored when searching
- ```m``` (multi line) means each line should be treated as individual inputs

### Grouping and Capturing
Grouping is a way to look for something with more specificity. For example, ```(abc)``` looks for 'abc' and not 'bac'.

### Bracket Expressions
Brackets are used to represent any character in a group. For example, ```[xyz]``` can find 'x', 'jyzx', or 'wxabr'. If it includes at least one requirement inside the brackets, it is included. You can also simplify and use '-' to specify ranges: ```[a-f]``` will act the same as ```[abcdef]``` while shortening the regex.

### Greedy and Lazy Match
This determines how many characters it will include when it has the option. A greedy preference means it will include as many repetitions of the pattern as possible, while a lazy preference means it matches the fewest number of repetitions as possible.

### Boundaries
These define what positions a pattern should appear in. For example, ```^``` and ```$``` are boundaries as well as ```\b```: this lets you look for words separated by non-word characters.

### Back-references
Back references replace longer groups (phrases in parentheses) so you can use them again easily. These look like a backslash followed by a number. In this example, the first grouping used in the regex can be repeated by using ```\1```: ```(\w{2,4})\s\1```. You can do this with the second group (```\2```), third (```\3```), and so on.

### Look-ahead and Look-behind
These let you specify conditions around the pattern you are searching for. If you want to find 'fruit' only when it's used as 'fruit salad', you would do this: ```fruit(?= salad)```. You can also use this looking backwards: ```salad(?<=fruit )```.

## Author

Sam Joseph is a (soon to be) web developer and computer enthusiast that loves solving challenging programming problems.
<https://github.com/josephash>