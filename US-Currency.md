# Regex: Matching US Currency in Various Formats

Regular expressions (regex) are patterns that help match and manipulate text. In this tutorial, we will explore the currency regex.

## Summary

This tutorial will guide you through the currency regex

```
^\$?([0-9]{1,3},([0-9]{3},)*[0-9]{3}|[0-9]+)(\.[0-9][0-9])?$
```

This regex is designed to match currency values in the format of "$X.XX" or "$X,XXX.XX", where X represents a digit.

For further explanation, [Regex 101](https://regex101.com/r/uV1jN3/1) is a lovely site that allows you to break up the regex into its components and test it against various inputs.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

### Anchors
The `^` and `$` symbols are anchors that match the start and end of a line respectively. In the currency matching regex, `^` is used to match the start of the string, and `$` is used to match the end of the string.

### Quantifiers
Quantifiers are used to specify the number of times a character or group can appear in the string. In this regex, we have the following quantifiers:

- `{}` curly braces are quantifiers that specify how many times a character or group should be matched.
- `{1,3}` specifies that the preceding digit (i.e., `[0-9]`) can appear between 1 and 3 times.
- `*` specifies that the preceding group can appear zero or more times.
- `+` specifies that the preceding digit can appear one or more times.
- `?` specifies that the preceding character can appear zero or one times.

### Grouping Constructs
Grouping constructs are used to group parts of the regex together so that they can be treated as a single unit. 

First lets examine some basics:
- `()` parentheses are used to group together a sequence of characters or groups.
- `(\$?)` the first group matches an optional "$" sign.
- `([0-9]{3},)*` matches a group of three digits followed by a comma, and can appear zero or more times.

So in this regex, we have two main groups:
- `([0-9]{1,3},([0-9]{3},)*[0-9]{3}|[0-9]+)` together, these groupings will match a number in the thousands, millions, billions, or more.
- `(\.[0-9][0-9])?` matches a decimal (period) followed by two digits, and can appear zero or one times.

### Bracket Expressions
Bracket expressions are used to match a single character from a set of characters. In this regex, we have the following bracket expressions:

- `[]` square brackets are used to match a single character from a set of characters.
- `[0-9]` therefore matches any digit between 0 and 9.
- `[0-9]{1,3}` matches any digit between 0 and 9, and can appear between 1 and 3 times.
- `[0-9][0-9]` matches two digits between 0 and 9.
- `[,]` matches a comma character.

### Character Classes
Character classes are used to match certain types of characters, such as digits or whitespace. In this regex, the character class `\d` matches any digit, which is equivalent to `[0-9]`. The character class `\s` matches any whitespace character, such as space, tab, or newline.

### The OR Operator
The OR operator `|` is used to match either one expression or another. In this regex, the expression `[0-9]{1,3},([0-9]{3},)*[0-9]{3}` matches currency values in the format of "$X,XXX", (a number in the thousands, millions, billions, etc) or `|` the expression `[0-9]+(\.[0-9][0-9])?` will matche currency values in the format of "$X.XX" (a single number value).

### Flags
Flags are optional settings that can be added to a regex pattern to change its behavior. The `g` flag is used to indicate that the pattern should be matched globally throughout the entire input string, rather than just stopping at the first match. The `m` flag is used to enable multiline mode, allowing the pattern to match across multiple lines. In this regex pattern, both `g` and `m` flags are used for that purpose.

### Character Escapes
Character escapes are used in regex to match special characters or characters that have a specific meaning in the regex syntax. In this regex pattern, the following character escapes are used:

- `\` The backslash character is used to escape special characters that have a specific meaning in regex syntax, such as the dollar sign (`$`) in this pattern. Without the backslash, the dollar sign would be interpreted as the end of the string anchor.
- `.` The period character is used to match any single character, but in this pattern, it is escaped to match a literal period character.
- `[` and `]` These characters are used to define a character class, which matches any single character that is contained within the brackets. Although in the this regex pattern, we do not use any character classes.

## Author

>Welcome! I'm [Lukas Virden](https://github.com/luksvrd) & I've spent 4 years in the civil engineering industry where I've gained alot of real world (slap in the face) experience. Over the past 1.5 years as a site engineer, the soul crushing/stagnating routine of driving across the midwest, performing labor intensive responsibilities was what pushed me to research a path forward. 
>
>I realized my interests and values aligned more so with companies in the technology space. As I considered ways to break in, I found the accessibility and variety of learning programming languages very attractive! 
>
>From my previous role in civil site design, I knew that work felt the most meaningful to me when I was working on a project (i.e., using various technologies & compiling project specific components/files to deliver a product). 
>
>After months of deliberation & exposure to free resources, I enrolled in the STL Washington University Full Stack Web Development Bootcamp. Upon completion (April 2023) I'll be seeking to transition to a career in software development. Proficient in React, Node.js, Express, MongoDB, Git, and Agile methodologies. 
>
>I'm truely energized to continue this lifelong journey of learning new technologies and collaborating with teammates to build innovative technological solutions!

