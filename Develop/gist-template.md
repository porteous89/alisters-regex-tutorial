# Understanding the Regular Expression for Matching an Email Address

Regular expressions are a powerful tool for pattern matching, searching, filtering, and manipulating text, they are widely used in programming. Regular Expressions provide a concise and flexible way to define patterns in strings. An email address is a common pattern that can be matched using regular expressions. In this tutorial, we will explore the general regex components that are used for matching an email address.

## Summary

The regular expression we will be exploring is:

/^([a-z0-9_.-]+)@([\da-z.-]+)\.([a-z.]{2,6})$/

This regex matches a valid email address that follows the typical email format of username@domain.tld. Let's break down each component of the regex and understand what it does.

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
Anchors are used to match the position of a pattern within the text. In regular expressions, there are two types of anchors - the caret (^) and dollar sign ($). This specifies that the pattern must match the entire string, not just a part of it. In our case, this means that the regex must match the entire email address.

### Quantifiers
Quantifiers are used to specify the number of times a pattern can occur in a text. In regular expressions, there are four types of quantifiers - the asterisk (*), the plus sign (+), the question mark (?), and the curly braces ({ }). The plus sign means that one or more characters in the preceding character set or group can occur, while the curly braces are used to specify the exact number of times a character can occur.

### OR Operator
The OR operator (|) can be used to specify multiple alternatives for a particular pattern. This allows you to match a pattern against multiple options, and only one of the options needs to match in order for the regex to succeed. One common use of the OR operator in matching an email address is to specify multiple valid TLDs for the domain name. 

### Character Classes
Character classes are used to match specific types of characters. In regular expressions, character classes are denoted by square brackets ([ ]). For example, the regex "[abc]" will match any string that contains the letters "a", "b", or "c". Character classes can also be used to match a range of characters. For example, the regex "[a-z]" will match any lowercase letter from "a" to "z". In our email regex, we use a range of characters to match the username and domain sections of the email address.

### Flags
Flags are used to modify the behavior of the regex. In regular expressions, flags are denoted by a letter after the closing delimiter (/). For example, the 'g' flag is used to perform a global search, while the 'i' flag is used for case-insensitive searching.

### Grouping and Capturing
#### Username Section
The username section of the regex is encapsulated by parentheses. This means that it's a capturing group, which allows us to extract the matched text later. Inside the parentheses, we have a character class that matches a range of characters including lowercase letters (a-z), digits (0-9), underscores (_), periods (.), and hyphens (-). The plus sign (+) following the character class means that one or more characters in this range can occur in the username section.

/^([a-z0-9_.-]+)@

#### Domain Section
The domain section of the regex is also encapsulated by parentheses as a capturing group. Inside the parentheses, we have another character class that matches a range of characters including digits (\d), lowercase letters (a-z), periods (.), and hyphens (-). The plus sign (+) following the character class means that one or more characters in this range can occur in the domain section.

([\da-z.-]+)\.

#### Top-Level Domain
The top-level domain section of the regex matches the TLD of the email address, which is typically a two to six-letter string such as .com or .edu. The regex matches this by looking for a period followed by a range of lowercase letters with a minimum of two and a maximum of six characters. This ensures that the TLD is a valid length and composed of valid characters.

([a-z.]{2,6})$/

### Bracket Expressions
Bracket expressions are used to match a single character from a set of characters. For example, [abc] matches 'a', 'b', or 'c'. One common use of bracket expressions in matching an email address is to match specific characters that are valid in an email address. Another use of bracket expressions in matching an email address is to match specific characters in the domain name, such as the top-level domain (TLD).

### Greedy and Lazy Match
Greedy matching, matches as many characters as possible while still allowing the regex to match successfully. This is the default behavior of most regex engines, including those used for matching email addresses. Lazy matching, matches as few characters as possible while still allowing the regex to match successfully. This can be useful in certain situations where the input may contain multiple matches of the same pattern, and you want to match each one separately.

### Boundaries
Boundary matchers are used to match a specific location, such as the beginning or end of a word. There are two types of boundaries commonly used in regex: word boundaries and line boundaries. In our email regex, we use the word boundary matcher (\b) to ensure that the email address is a standalone word. This ensures that the regex matches the username and domain name separately, without matching any other characters in between.

### Back-references
Back-references allow us to match the same text that was matched by a capturing group earlier in the regex. Back-references are useful when you want to ensure that a certain part of the input matches a previously matched part of the input. One common use of back-references in matching an email address is to validate the domain name against a list of valid top-level domains (TLDs).

### Look-ahead and Look-behind
In matching an email address, look-ahead and look-behind are advanced regex techniques that allow you to match patterns based on their position relative to other patterns in the input string, without actually including those patterns in the match. One common use of look-ahead in matching an email address is to validate the format of the email address without including the "@" symbol in the match.

## Author
This tutorial was written by [Alister Porteous](https://github.com/porteous89/alisters-regex-tutorial). You can find more of their work on their [GitHub profile](https://github.com/porteous89).
