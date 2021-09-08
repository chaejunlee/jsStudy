# Chap. 2 Lexical Structure

### Lexical structure of programming language:  
- set of elementary rules that specifies how you write programs in that language.

- lowest-level syntax of a language.

  - what variable names look like,

  - the delimiter characters for comments,

  - and how one program statement is separeted from the next.

- This chapter covers:

  - Case sensitivity, spaces, and line breaks

  - Comments

  - Literals 

  - Indetifiers and reversed words

  - Unicode 

  - Optional semicolons

## 2.1 The Text of JavaScript Program 

###  Case sensitivity

- JS is a case-sensitive language.

- language keywords, variables, function names, and other *identifiers* must always be typed with a consistent capitalization of letters.

- `online !== Online !== OnLine !== ONLINE`

### Spaces 

- JS ignores **spaces** that appear between tokens in programs. For the most part, JS also ignores **line breaks**.

- Because you can use spaces and newlines freely in your program, you can **format and indent your program in a neat and consistent way** that makes the code **easy to read and understand**.

### Whitespaces

- JS recognizes **regular space character (`\u0020`), tabs, assorted ASCII control characters, and various Unicode space characters** as whitespaces.

## 2.2 Comments

- JS supports **two styles of comments**.

1. **//**
    - Any text between a // and the end of a line is treated as a comment and ignored by JS.
2. ** /* */ **
    - Any text between the characters /\* and \*/ is also treated as comment