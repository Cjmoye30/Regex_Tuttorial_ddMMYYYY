# Regex - Date Format Tutorial

Regex is used as a way to quickly find and/or replace strings or characters through the use of searching with metacharacters. Regex is a string of metacharacters used to define a particular search pattern.

In this tutorial, we will look at how a Regex Expression can be used to format 

## Summary

Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary.

This tutorial will be looking specifically at the following regex which is used to find dates in the format of dd-MM-YYYY:.
The Regex string is composed of 3 differenct string combined with an OR operator ( | ), and I have separated them out below in the code snippet.

There are 3 different string - one for each component of the date format - day - month - year:

```
^(?:(?:31(\/|-|\.)(?:0?[13578]|1[02]))\1|(?:(?:29|30)(\/|-|\.)(?:0?[1,3-9]|1[0-2])\2))(?:(?:1[6-9]|[2-9]\d)?\d{2})$|

^(?:29(\/|-|\.)0?2\3(?:(?:(?:1[6-9]|[2-9]\d)?(?:0[48]|[2468][048]|[13579][26])|(?:(?:16|[2468][048]|[3579][26])00))))$|

^(?:0?[1-9]|1\d|2[0-8])(\/|-|\.)(?:(?:0?[1-9])|(?:1[0-2]))\4(?:(?:1[6-9]|[2-9]\d)?\d{2})$
```

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Character Escapes](#character-escapes)
- [Author](#author)

## Regex Components

- This Regex is composed of the following components:
    - Character Classes - specific sets of characters which can be used in the search.
    - Anchors - find the starting and ending points of a string.
    - Escaping Characters - can be used to insert reversed, special, and unicode characters.
    - Groups & References - match a pattern multiple times within a string.
    - Quantifiers & Alternation - specify how many of a character should be matched.


### Anchors

- Anchors are used to identify the beginning and the end of the string.
- Our entire regex string is actually composed of 3 different strings - one for the day, month, and year respectively - and they are all wrapped with the following opening and closing anchors:
    - Opening Anchor: ```^```
    - Closing Anchor: ```$```

### Quantifiers

- Specifies how many of the preceeding character/token should be matched.
- Examples from our strings:
    - ```?``` - match between 0 and 1 of the preceding token.
    - ```{2}``` - match 2 of the preceding token.

### Grouping Constructs

- Grouping can either be used as a "non-capture group" or "capture group". 
- Non-capture Group - groups up multiple tokens without creating a capture group. In our examples, these are typically nested within eachother, with a capture group also nested inside:
    - ``` (?:(?:31(\/|-|\.)(?:0?[13578]|1[02]))\1|(?:(?:29|30)(\/|-|\.)(?:0?[1,3-9]|1[0-2])\2)) ```
    - ``` (?:31(\/|-|\.)(?:0?[13578]|1[02])) ```

- Capture Group - groups multiple token for extracting: 
    - ```(\/|-|\.) ```

### Character Classes

- Matches a character from a specific set. All of our character classes in our strings consist of numbers.
- Examples:
    - ```[13578]```
    - ```[02]```
    - ```[1,3-9]```
    - ```[0-2]```
    - ```[6-9]```

### The OR Operator

- Defined as a vertical slash ```|```
- Matches the expression before or after the ```|```
- The easiest examples are the vertical slashes which join all of our strings together - which are the vertical slashed coming before the ```^```
- Many other examples within the grouping constructs

### Character Escapes

- The backslash - ```\``` - ignores any text coming after it. In our example, if we need slashes within our date format, it would be coded ```\/```.
- There are only 2 examples of this within our strings:
    - ```\.``` escapes the "." and allows it to be matched
    - ```\/``` escapes the "/" and allows it to be matched

## Author

- My name is Cambric Moye, and I a Full-Stack Web Developer with a certificate from The Coding Bootcamp at UNC-Charlotte. 
- Please, feel free to connect with me on [Github](https://github.com/Cjmoye30)

## References

[What Is Regex? A Primer on Writing & Using Regular Expressions](https://www.variables.sh/what-is-regex/#:~:text=Regexes%20are%20composed%20of%20several,classes%2C%20quantifiers%2C%20and%20alternation.)

[Regexr.com](https://regexr.com/?346hf)

