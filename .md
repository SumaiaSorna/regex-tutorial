# Regular Expression (Regex)

Regular expressions are patterns used to match character combinations in strings. In JavaScript, regular expressions are also objects.

## Project Objective

A regular expression (shortened as regex or regexp; also referred to as rational expression) is a sequence of characters that specifies a search pattern in text. Usually such patterns are used by string-searching algorithms for "find" or "find and replace" operations on strings, or for input validation.

## Summary

Throughout this tutorial I explained a couple of specific Regexes with examples, so that users can understand how these works. At the end, I added an example covering the Regex components described here.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)
- [Combined example](#combined-example)

## Regex Components

Although varies use of the Regex in different programming languages, the common regular expression components are discussed below:

### Anchors

Anchors are characters that specify the location within a particular string to search. To find a character "A" in a string, you can use characters from the following list to find a match within a line:

```
^A : Match at the beginning of a line.
A$ : Match at the end of a line.
```

### Quantifiers

Quantifiers allow you to specify how many times you want a particular Regex string to match. Regex matching is eager and will match as much as possible, which is not always the desired behaviour. Some quantifiers allow you to limit how much is matched.

```
*- Match 0 or more times.
+ - Match 1 or more times
{ n } - Match exactly n times.

```

### Grouping Constructs

Grouping constructs delineate subexpressions of a regular expression and typically capture substrings of an input string. Here is an example for you:

```
Example String: "1ABB 3ABBC 5AB 5AC"
Expression/subexpression: “(?> subexpression )”
Grouping Constructs Regex pattern: ( [13579](?>A+B+)
Matches: "1ABB", "3ABB", and "5AB"

```

### Bracket Expressions

A bracket expression represents a character set via a list of characters enclosed by the square brackets: '[' and ']'. It normally matches the target string with any single character from the list. Please see the following example:

```
Expression: [abc]
Matches: a, b, or c


```

### Character Classes

With a “character class”, also called “character set”, you can tell the Regex engine to match only one out of several characters. Simply place the characters you want to match between square brackets.

```
Expression: If you want to match an a or an e, use [ae] like this gr[ae]y .
Matches: gray or grey

```

### The OR Operator

The OR operator allows you to compose regular expression patterns to match any one out of a set of alternative choices. For example, the (t|T) will match either t or T from the input string.

```
Example String: "The quick brown fox jumps over the lazy dog";
Expression: "(t|T)";
Matches: "T" from the “The” at the beginning
Matches: "t" from the “the” near the end.

```

### Flags

Regular expressions may have flags that affect the search (e.g. search with case sensitive or not). There are six of them in JS.

```
Example String: "We will, we will rock you";

Expression 1: alert( str.match(/we/gi) );
Matches 1: We,we (not case sensitive)

Expression 2: str.match(/we/i); // without flag g, now Case sensitive
Matches 2: Case sensitive We

```

### Character Escapes

The backslash in a regular expression precedes a literal character. You also escape certain letters that represent common character classes, such as \w for a word character or \s for a space. The following example matches word characters (alphanumeric and underscores) and spaces.

```
Example String: "Are you there, Saafee?, asked Sumaia.",
Expression: "(here|there).+(\w+).+(said|asked)(\s)(\w+)\." );
Output: "there, Saafee?, asked Sumaia."

```

### Combined example

In the following Regex example, if my target is matching any email address from the domains of yahoo.com and gmail.com.

Regex Expression:

```
(\W|^)[\w.\-]{0,25}@(yahoo|gmail)\.com(\W|$)
```

What this means:

- ^ matches the start of a new line & $ matches the end of a line. See more on: `Anchors`

- {0,25} indicates that from 0 to 25 characters in the preceding character set can occur before the @ symbol. See more in `Quantifier`

- [\w.\-] matches any word character (a-z, A-Z, 0-9, or an underscore), a period, or a hyphen. Similarly, groups can also be defined, see `Grouping Constructs`

- Square bracket in here [\w.\-] means any word character (a-z, A-Z, 0-9, or an underscore) will check matches the target string. The \- (which indicates a hyphen) must occur last in the list of characters within the `Square brackets`

- Sometime, Character Classes allow flexibility of searching combined characters, see `Character Classes`

- The (...) formatting groups the domains, and the | character that separates them indicates an “or.” See more for The `OR Operator`

- \W matches any character that’s not a letter, digit, or underscore. It prevents the Regex from matching characters before or after the email address. See more on `Character Escapes`. Also, note here for the above example, the \ before the dash and period “escapes” these characters—that is, it indicates that the dash and period aren't a Regex special character themselves. There's no need to escape the period within the `Square brackets`

## Author

If you have any questions about this application, please feel free to contact me in my <a href="mailto:sorna.sumaia@gmail.com">email.</a>
