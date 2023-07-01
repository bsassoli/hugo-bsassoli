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

### Exercises

(𝜆𝑎𝑏𝑐.𝑐𝑏𝑎)𝑧𝑧(𝜆𝑤𝑣.𝑤)

(𝜆𝑏𝑐.𝑐𝑏𝑧)(𝑧)(𝜆𝑤𝑣.𝑤)

(𝜆𝑐.𝑐𝑧𝑧)(𝜆𝑤𝑣.𝑤)

(𝜆𝑤𝑣.𝑤)(𝑧𝑧)

𝑧𝑧
***
(𝜆𝑥.𝜆𝑦.𝑥𝑦𝑦)(𝜆𝑎.𝑎)𝑏

(𝜆𝑦.(𝜆𝑎.𝑎)yy)(𝑏)

(𝜆𝑎.𝑎)𝑏𝑏

𝑏𝑏
***
(𝜆𝑦.𝑦)(𝜆𝑥.𝑥𝑥)(𝜆𝑧.𝑧𝑞)

(𝜆𝑥.𝑥𝑥)(𝜆𝑧.𝑧𝑞)

(𝜆𝑧.𝑧𝑞)(𝜆𝑧.𝑧𝑞)

(𝜆𝑧.𝑧𝑞)(𝑞)

𝑞𝑞
***
(𝜆𝑧.𝑧)(𝜆𝑧.𝑧𝑧)(𝜆𝑧.𝑧𝑦)

(𝜆𝑧.𝑧𝑧)(𝜆𝑞.𝑞𝑦)

(𝜆𝑞.𝑞𝑦)(𝜆𝑞.𝑞𝑦)

(𝜆𝑞.𝑞𝑦)(y)

yy
***
(𝜆𝑥.𝜆𝑦.𝑥𝑦𝑦)(𝜆𝑦.𝑦)𝑦

(𝜆𝑥.𝜆𝑦.𝑥𝑦𝑦)(𝜆𝑞.𝑞)(𝑦)

(𝜆𝑦.(𝜆𝑞.𝑞)𝑦𝑦)(𝑦)

((𝜆𝑞.𝑞)𝑦)(𝑦)

𝑦𝑦

***

(𝜆𝑎.𝑎𝑎)(𝜆𝑏.𝑏𝑎)𝑐

(𝜆𝑎.𝑎𝑎)(𝜆𝑏.𝑏𝑎)𝑐

(𝜆𝑏.𝑏𝑎)(𝜆𝑏.𝑏𝑎)(𝑐)

(𝜆𝑏.𝑏𝑎)(𝑎)(𝑐)

𝑎𝑎𝑐

***

(𝜆𝑥𝑦𝑧.𝑥𝑧(𝑦𝑧))(𝜆𝑥.𝑧)(𝜆𝑥.𝑎)

(𝜆𝑥.𝜆𝑦.𝜆𝑧.𝑥𝑧(𝑦𝑧))(𝜆𝑥.𝑐)(𝜆𝑥.𝑎)

(𝜆𝑦.𝜆𝑧.(𝜆𝑥.𝑐)(𝑧)(𝑦𝑧))(𝜆𝑥.𝑎)

(𝜆𝑧.(𝜆𝑥.𝑐)(𝑧)((𝜆𝑥.𝑎)𝑧))

(𝜆𝑧.𝑐(𝜆𝑥.𝑎(𝑧)))

(𝜆𝑧.𝑐𝑎)




```haskell
sayHello :: String -> IO()
sayHello x = "hello " ++ x
```

