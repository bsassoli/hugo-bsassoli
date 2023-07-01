# Haskell Book: Part 1


So this morning I got started with the [Haskell book](https://lhbg-book.link). Here are some notes and exercises.

## Chapter 1

This is just a very short and simple introduction to the lambda calculus.

- Syntax of λ-calculus

```BNF
<expression> := <name> | <function> | <application>
<function> := λ <name>.<expression>
<application> := <expression><expression>
```

- **α-equivalence**: basically the notion that $\lambda{x}.x$, $\lambda{y}.y$ and $\lambda{z}.z$ all express the same function.
- **β-reduction**: when you apply a function to some expression you replace all bound occurrences in the body with that expression and eliminate the head. To indicate that we are substituting e.g. $x$ with $z$ in $\lambda{x}.x$ we write: $$[x := z]$$
- Applications are *left-associative*: $$(\lambda{x}.x)(\lambda{y}.y)z$$ is equivalent to $$((\lambda{x}.x)(\lambda{y}.y))z$$

[Exercises]({{< ref "/pages/chapter-1-exercises" >}})


```haskell
sayHello :: String -> IO()
sayHello x = "hello " ++ x
```

