---
title: "Haskell Book: Chapters 1 & 2"
date: 2023-06-30T12:13:35+02:00
draft: false
description: "Notes on chapters 1 and 2 of the Haskell book"
featuredImage: "/images/haskell-hello-world.png"
tags: [programming, programming languages, Haskell]
categories: [Learning Haskell, Notes, Haskell Book]
---

So this morning I got started with the [Haskell book](https://lhbg-book.link). Here are some notes and exercises.

## Chapter 1

This is just a very short and simple introduction to the lambda calculus.

- **Syntax** of λ-calculus

```BNF
<expression> := <name> | <function> | <application>
<function> := λ <name>.<expression>
<application> := <expression><expression>
```

- **α-equivalence**: basically the notion that $\lambda{x}.x$, $\lambda{y}.y$ and $\lambda{z}.z$ all express the same function.
- **β-reduction**: when you apply a function to some expression you replace all bound occurrences in the body with that expression and eliminate the head. To indicate that we are substituting e.g. $x$ with $z$ in $\lambda{x}.x$ we write: $$[x := z]$$
- Applications are *left-associative*: $$(\lambda{x}.x)(\lambda{y}.y)z$$ is equivalent to $$((\lambda{x}.x)(\lambda{y}.y))z$$
- Each lambda can only bind one parameter and can only accept one argument. Functions that require multiple arguments have multiple, nested heads. This is known as **currying**
- A **combinator** is a lambda term with no free variables
- **β normal form**. Beta normal form is when you cannot beta reduce (apply lambdas to arguments) the terms any further. This corresponds to a fully evaluated expression, or, in programming, a fully executed program.
- Some expressions **diverge**, e.g. not all reducible lambda terms reduce to a normal form. This isn’t because they’re already fully reduced, but because they diverge. E.g. the *omega* expression (𝜆𝑥.𝑥𝑥)(𝜆𝑥.𝑥𝑥) diverges.

>semantically, Haskell is a lambda calculus. Actually, Haskell is a typed lambda calculus—more on types later— with a lot of surface-level decoration sprinkled on top, to make it easier for humans to write, but the semantics of the core language are the same as the lambda calculus. That is, the meaning of Haskell programs is centered around evaluating expressions.

### [Exercises]({{< ref "chapter-1-exercises" >}})

## Chapter 2

```haskell
sayHello :: String -> IO()
sayHello x = "hello " ++ x
```

Most of this wasn't new. But it pushed me to clarify what is meant by **"pure"** function which is a somewhat confusing notion. So all of these are impiure functions in Python.

```python
a = 20
def impure1():
    global a
    a = a + 20
impure1() 
print(a)
# no return, calling it will cause changes to a which is outside it's scope

num = 10
def impure2():
    print(num)
impure2()
# no return, changing num will change it's behaviour even though num isn't an argument to impure

num3 = 10
def impure3 (num1, num2):
    x = (num1 + num2) / num3
    return x
print(impure3(2, 3))
# returns a value but what it returns depends on something that's not an argument
```

Other than that:

- REPL + `ghci`
- infixing with backticks and prefixing with parens
- association and precedence (with `:info`)
- `let` vs `where`
