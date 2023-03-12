# Understanding the Regular Expression for Matching an Email Address

Regular expressions are a powerful tool for searching, filtering, and manipulating text. They provide a concise and flexible way to define patterns in strings. In this tutorial, we will dive into a specific regular expression used for matching an email address.

## Summary

The regular expression we will be exploring is:

/^([a-z0-9_.-]+)@([\da-z.-]+)\.([a-z.]{2,6})$/

This regex matches a valid email address that follows the typical email format of username@domain.tld. Let's break down each component of the regex and understand what it does.

## Table of Contents

- [Email Regex](#email-regex)
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

## Email Regex

### Username Section
The username section of the regex is encapsulated by parentheses. This means that it's a capturing group, which allows us to extract the matched text later. Inside the parentheses, we have a character class that matches a range of characters including lowercase letters (a-z), digits (0-9), underscores (_), periods (.), and hyphens (-). The plus sign (+) following the character class means that one or more characters in this range can occur in the username section.

/^([a-z0-9_.-]+)@

### Domain Section
The domain section of the regex is also encapsulated by parentheses as a capturing group. Inside the parentheses, we have another character class that matches a range of characters including digits (\d), lowercase letters (a-z), periods (.), and hyphens (-). The plus sign (+) following the character class means that one or more characters in this range can occur in the domain section.

([\da-z.-]+)\.

### Top-Level Domain
The top-level domain section of the regex matches the TLD of the email address, which is typically a two to six-letter string such as .com or .edu. The regex matches this by looking for a period followed by a range of lowercase letters with a minimum of two and a maximum of six characters. This ensures that the TLD is a valid length and composed of valid characters.

([a-z.]{2,6})$/

## Regex Components
### Anchors
The regex starts and ends with the caret (^) and dollar sign ($), respectively. This specifies that the pattern must match the entire string, not just a part of it. In our case, this means that the regex must match the entire email address.

### Quantifiers
The plus sign (+) and the curly braces ({}) are used as quantifiers in the regex. The plus sign means that one or more characters in the preceding character set or group can occur, while the curly braces are used to specify the exact number of times a character can occur.

### OR Operator
The pipe symbol (|) is used as the OR operator in regular expressions. It allows for matching either one expression or another.

### Character Classes
Character classes are used to match specific types of characters. In our email regex, we use a range of characters to match the username and domain sections of the email address.

### Flags
Flags are used to modify the behavior of the regex. For example, the 'g' flag is used to perform a global search, while the 'i' flag is used for case-insensitive searching.

### Grouping and Capturing
Parentheses are used to group expressions and create capturing groups. Capturing groups allow us to extract the matched text later.

### Bracket Expressions
Bracket expressions are used to match a single character from a set of characters. For example, [abc] matches 'a', 'b', or 'c'.

### Greedy and Lazy Match
By default, regular expressions use greedy matching, which matches as much as possible. Lazy matching can be used to match as little as possible.

### Boundaries
Boundary matchers are used to match a specific location, such as the beginning or end of a word. In our email regex, we use the word boundary matcher (\b) to ensure that the email address is a standalone word.

### Back-references
Back-references allow us to match the same text that was matched by a capturing group earlier in the regex.

### Look-ahead and Look-behind
Look-ahead and look-behind assertions allow us to match patterns that are followed by or preceded by another pattern, without including the other pattern in the match.

## Author
This tutorial was written by [Alister Porteous](https://github.com/porteous89/alisters-regex-tutorial). You can find more of their work on their [GitHub profile](https://github.com/porteous89).
