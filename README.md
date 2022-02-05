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

### Combined example

## Author
