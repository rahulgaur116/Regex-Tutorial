# Regex-Tutorial



## Summary

Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary.
Regular expressions, commonly known as regex, are powerful tools used for pattern matching within strings. They are widely utilized in programming for tasks such as validation, searching, and text manipulation. We will look a a string of code using regex, this code looks for a match for dates between October 1st 2022 and September 31st 2024.

Example:REX-  1[0-2]/\d?\d/2022|0?[1-9]/\d?\d/2024

The below content will explain what each section of this code does and more. The regex pattern 1[0-2]/\d?\d/2022|0?[1-9]/\d?\d/2024 demonstrates several fundamental components of regex, including anchors, quantifiers, grouping constructs, bracket expressions, character classes, the OR operator, flags, and character escapes. This essay will dive into each of these components to explain their functions and how they contribute to the overall pattern.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)
- [Sources and References](#sources-and-References)
- [Conclusion](#conclusion)

## Regex Components


### Anchors
Anchors in regex are used to specify the position in the string where a match will occur. 
There are two primary anchors: ^ which signifies the start of a string, and $ which denotes the end. In our example regex 1[0-2]/\d?\d/2022|0?[1-9]/\d?\d/2024 we do not explicitly use these anchors, they are essential in ensuring that patterns match at specific positions within the text. For instance, if we wanted to ensure that the date pattern only matches at the start of a line, we would prepend ^ to the regex.

### Quantifiers
Quantifiers define the number of times an element can occur in a regex pattern. There are diffrent variations of the quatifiers and can be greedy or lazy.
For example
"+" Matches 1 or more of the preceding token.
"*" Matches 0 or more of the preceding token.
"?" Matches 0 or 1 of the preceding token, effectively making it optional.
"?" Makes the preceding quantifier lazy, causing it to match as few characters as possible. By default, quantifiers are greedy, and will match as many characters as possible.

In our example, \d?\d is a crucial part of the pattern where ? and the absence of a quantifier play significant roles. Here, \d represents any digit, and ? is a quantifier indicating that the preceding element (a digit) may appear zero or one time. Therefor, \d?\d matches either a single digit or two digits, accommodating day and month formats such as 1, 15, or 31.

### Grouping Constructs
Grouping constructs, denoted by parentheses (), are used to group parts of a regex together. This allows for applying quantifiers to the entire group or capturing the matched substrings for further use. For example- 
(ABC) Capturing groups multiple tokens together and creates a capture group for extracting a substring or using a backreference.
(?<name>ABC) named capturing group captures groups of a specific name.
\1 is a numeric Referance
(?:ABC) Groups multiple tokens together without creating a capture group. 
In our regex for fiscal year date, the entire pattern is not explicitly grouped, but the use of | (OR operator) acts implicitly to group 1[0-2]/\d?\d/2022 and 0?[1-9]/\d?\d/2024 as alternatives. Grouping can also be used for more complex patterns and nested expressions, enabling the application of quantifiers and alternations to specific sections of the regex.

### Bracket Expressions
Bracket expressions, also known as character classes, allow for matching any one of several characters enclosed within square brackets []. In the example regex, 1[0-2] and 0?[1-9] are bracket expressions. 1[0-2] matches either 10, 11, or 12, corresponding to the months October, November, and December. Similarly, 0?[1-9] matches single-digit months, allowing an optional leading zero, and digits from 1 to 9, covering all possible month representations in dates.

### Character Classes
Character classes are predefined sets of characters that can be used in a regex. The most common character class used in our example is \d, which matches any digit (equivalent to [0-9]). Character classes simplify the regex and make it more readable by replacing longer bracket expressions. They are essential for matching various categories of characters, such as digits, word characters (\w), or whitespace characters (\s). Few more exmpales of Character Classes are listed below.

[ABC] Characters inside brakets will match any character in the set.
[^ABC] Adding a caret will match any character that is not in the set.
[A-Z] Add a dash between two characters will select a Range.
. Will Match any characters expect linebreaks. Its like a wildcard and will accpet any input.
[\s\S] A character set that can be used to match any character, including line breaks, without the dotall flag. An alternative is [^] carrot in brackets, but it is not supported in all browsers.
\w Matches any word character (alphanumeric & underscore). Only matches low-ascii characters (no accented or non-roman characters).
\W Matches any character that is not a word character (alphanumeric & underscore).
\d Matches any digit character (0-9)
\p Matches a character in the specified unicode category.

### The OR Operator
The OR operator, represented by the vertical bar |, allows for matching one of several patterns. In our regex, 1[0-2]/\d?\d/2022|0?[1-9]/\d?\d/2024 uses | to create a choice between two date formats. It ensures that the pattern matches either dates from 2022 with months October to December or dates from 2024 with months January to September. The OR operator is pivotal in creating flexible and inclusive patterns that accommodate multiple alternatives.

### Flags
Flags in regex are optional parameters that modify the behavior of the pattern matching. Expression flags change how the expression is interpreted. Flags follow the closing forward slash of the expression.They are typically used to enable case-insensitive matching (i), multi-line mode (m), or other special matching rules. Although our example does not include any flags, they can be appended to the regex pattern or specified in regex functions in various programming languages. For instance, /pattern/i would make the regex case-insensitive. Few more exmpales of Flags are listed below.
i Ignores case
g Global search retain the index of the last match, allowing subsequent searches to start from the end of the previous match. Without the global flag, subsequent searches will return the same match.
m Multiline flag When the multiline flag is enabled, beginning and end anchors (^ and $) will match the start and end of a line, instead of the start and end of the whole string.
u Unicode
y The expression will only match from its lastIndex position and ignores the global (g) flag if set. Because each search in RegExr is discrete, this flag has no further impact on the displayed results.
s Dot (.) will match any character, including newline.

### Character Escapes
Character escapes allow for matching special characters that have a particular meaning in regex syntax. These are indicated by a backslash \. In our example, \d is a character escape that matches any digit. Escapes are crucial for handling characters like . (dot), * (asterisk), and ? (question mark), which have special functions in regex. By escaping these characters, they can be matched literally in the text.

### Conclusion
In conclusion, the regex 1[0-2]/\d?\d/2022|0?[1-9]/\d?\d/2024 showcases a variety of regex components, each playing a vital role in constructing the overall pattern. Understanding these components—anchors, quantifiers, grouping constructs, bracket expressions, character classes, the OR operator, flags, and character escapes—enhances one's ability to create and interpret complex regex patterns, making them indispensable tools in text processing and manipulation.

## Author

Written by- Rahul Sharma- Fullstack Developmemt Bootcamp student Columbia University
Github- https://github.com/rahulgaur116

## Sources and References
* [regexr](https://regexr.com/)
* [regex101] (https://regex101.com/)
* [wiki](https://en.wikipedia.org/wiki/Regular_expression)
* [web](https://www.liquidweb.com/kb/what-are-regular-expressions/)
* [mozilla](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions)