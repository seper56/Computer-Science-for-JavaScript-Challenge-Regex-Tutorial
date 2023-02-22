# Regex Tutorial
As a full stack web development student, I have developed a tutorial explaning a specifics of regex so that we can understand the search pattern regex defines


## Summary
Typically, Regex or regular expressions aere used by strings-searching algorithms to search for or replace stings or to validtae input. is is a techique commonly used in theoretical computer science.

lets look a string code using regex to look for a match HTML tag

Example: /^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/

Below you will find other content that will explain what each section does and more.

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
- "^"abc$ -- "^" start "$" end of the string

  - "^" Matches the beginning of a string or the beginning of a line if the multiline flag (m) is on. This corresponds to a position, not a character.

  - "$" Matches the end of a string or the end of a line if the multiline (m) flag is on. This corresponds to a position, not a character

- \b\B -- word, not word boundary

  - \b  Matches the position of a word boundary between a word character and non-word character or position (start / end of the string). Read the definition of character class (w) to learn more.

  - \B  Conforms to any position that is not a word boundary. This is in agreement with a position, rather than a specific character.
Read the text: Boundaries > More information about Boundaries.

### Quantifiers
Quantifiers indicate that the preceding token must match a specific number of times. Quantifire can be greedy or lazy, which is explained below.

- "a*a+a?" -0 or more, 1 or more, 0 or 1
 - "+" Matches 1 or more of the preceding token.
 - "*" Matches 0 or more of the preceding token.
 - "?" Matches 0 or 1 of the preceding token, effectively making it optional.
 - "?" Makes the preceding quantifier lazy, causing it to match as few characters as possible. By default, quantifiers are greedy, and will match as many characters as possible.
- "a{5}a{2,}" -Looks for exactly five, two or more
- "{2,6}" -forces the input of characters between two & six characters long.
- "a+?a{2,}?" -match as few as possible
- "ab|cd" -match ab or cd

### OR Operator
- "|" behaves like an OR boolean. matches the expression preceding or following the |. It can affect an entire expression or a group of people. The patterns will be put through their paces. Similar to how Java matches both sets of characters. It will search for either this or that.

### Character Classes
A character from a particular set is matched by their class. There are a number of character classes that have already been defined, and you can also create your own sets
 - [ABC] Characters inside brakets will match any character in the set.
 - [^ABC] Any character not included in the set will match when a caret is added.
 - [A-Z] Add a dash between two characters will select a Range.
 - . Will Match any character with the exception of line breaks. Similar to a wildcard, it will take any input.
  - [\s\S] a character set that does not require the dot all flag to match any character, including line breaks. The alternative is [] carrot in brackets, but not all browsers support it.
 - \w matches any character in a word (alphabet and underscore). Matches only characters with low ascii (no accented or non-roman characters).
 - \d Matches any digit character (0-9)
 - \p Matches a character in the specified unicode category.
 
### Flags
Expression flags alter the interpretation of the expression. The expression's final forward slash is followed by flags
 - i Ignores case
 - g The global search keeps the index of the most recent match, so subsequent searches can begin at the end of the most recent match. The same match will be found in subsequent searches without the global flag.
 - m Multiline flag When the multiline flag is set to true, the beginning and end anchors (^and$) will correspond to the beginning and end of a line rather than the entire string.
 - u Unicode
 - y The global (g) flag is ignored if it is set because the expression will only match from its lastIndex position. This flag has no further effect on the results that are displayed because RegExr performs discrete searches for each query.
 - s Dot (.) will match any character, including newline.

### Grouping and Capturing
 - (ABC) To use a backreference or extract a substring, a capture group is formed by grouping multiple tokens together
 - (?<name>ABC) named capturing group captures groups of a specific name.
 - \1 is a numeric Referance
 - (?:ABC) combines a number of tokens without forming a capture group.

### Bracket Expressions
 A regular expression that matches a single character or collating element is a bracket expression enclosed in square brackets. This bracket expression is complemented if the first character is a circumflex.

### Greedy and Lazy Match
 - "greedy" means matching the longest string that is possible. The engine is instructed by a greedy quantifier to match as many instances as possible of its quantified token or subpattern. This is known as being greedy.

 - "lazy" means completing the shortest string possible. The engine is instructed to match as few quantified tokens as necessary by a lazy quantifier. As shown in the table below, adding a? to a regular quantifier makes it lazy. it's a question mark.

### Boundaries
 Like the caret and the dollar sign, the \b is an anchor. It matches at what is known as a "word boundary." This match has a length of zero.

The characters that are considered word characters by word boundaries are those that are matched by the shorthand character class \w.

The character "b4" can be used to match a 4 that is not part of a larger number because digits are considered word characters. Therefore, stating "before and after a word" is less precise than saying "b matches before and after an alphanumeric sequence."

The negative form of \b is \b. \B is equivalent in every position where b is not. In other words, \B matches anywhere between two words and anywhere between two characters that aren't words.

The Regex Engine provides additional boundries. Tcl, GNU, and POSIX are a few examples.

### Back-references
Backreferences match the same text as a capturing group has previously matched. Let's say you want to match the text between two opening and closing HTML tags. We can use the same name for the closing tag by inserting the opening tag into a backreference.

For Example: <([A-Z][0-9]*)\b[^>]*>.*?</\1> this regex only uses one pair of parentheses to identify the string that is matched by [A-Z][0-9]*. This is the opening HTML tag. The backreference \1 references the first capturing group. \1 matches the exact same text as the first group that captured it. the / prior to that, it was a literal character. We are only trying to match the forward slash in the final HTML tag.

### Look-ahead and Look-behind
  - "(?=ABC)" is a positive lookahead that finds a group after the main expression but does not include it in the result.
  - "(?!ABC)" is a negative lookahead and it indicates a gathering that can not match after the fundamental articulation (assuming it coordinates, the outcome is disposed of)
  - "(?<!ABC)" is a negative look behind that specifies a group that cannot match the main expression before it (if it does, the result is discarded).

  The main expressions are compelled to be what you have defined them to be when you use lookaheads and lookbehinds. It will not be accepted as a valid input if it is not exactly what it is.

## Author
Semir Seper

My Github https://github.com/seper56