---
title: "Haskell Book: Chapters 3 & 4"
date: 2023-07-02T09:00:00+02:00
description: "Notes on chapters 3 and 4 of the Haskell book"
# featuredImage: "https://www.researchgate.net/publication/344704718/figure/fig1/AS:947446209327104@1602900187484/Martin-Loef-type-theory.png"
categories: [Learning Haskell, Notes, Haskell Book]
tags: [programming, programming languages, Haskell]
draft: false
---

## Chapter 3

- type `Char` (in *single quotes*) vs type `String` (which is as usual syntactic sugar for a list of chars, hence `String` is a **type alias** for `[Char]`)
- need `main` when building a project with Stack
- the `IO ()` type, "used when the result of running a program involves effects beyond evaluating a function or expression"
- `print` vs `putStr` vs `putStrLn` - the first just prints whatever to the display hence, the others are String specific (`putStrLn` will add a newline char):

  ```haskell
  print "hello"
  -- "hello" with quotation marks
  ```

- `do` syntax -> used when sequencing actions. Not strictly necessary, used for readability.
- concatenate strings with ++ and `concat`
- top-level *vs.* local bindings
- first mention of **type classes**:
  > Type classes provide definitions of operations, or functions, that can be shared across sets of types
- **List functions**
  - `cons` or `:`
  - `head`
  - `tail`
  - `take`
  - `drop`
  - `!!` (index)
  - These functions are *unsafe*:
    > while all of these are standard Prelude functions, many of them are considered unsafe. They are unsafe, because they do not know how to handle an empty list. Instead, they throw out an error message, or exception, when given an empty list as input

## Chapter 4

- **Data declarations**
  - *type* constructor
  - *data* constructor
- **Sum (union)** types:

  ```haskell
    data Bool = False | True
  ```
