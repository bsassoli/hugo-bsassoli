---
title: "Haskell Book: Chapter 1 Exercises"
date: 2023-07-01T07:07:59+02:00
draft: true
hiddenFromHomePage: true
toc: true
tags: [programming, programming languages, Haskell]
categories: [Learning Haskell]
---
## Combinators

1. 𝜆𝑥.𝑥𝑥𝑥
2. 𝜆𝑥𝑦.𝑧𝑥
3. 𝜆𝑥𝑦𝑧.𝑥𝑦(𝑧𝑥)
4. 𝜆𝑥𝑦𝑧.𝑥𝑦(𝑧𝑥𝑦)
5. 𝜆𝑥𝑦.𝑥𝑦(𝑧𝑥𝑦)

2 and 5 are not combinators because in both cases $z$ appears free.

## Normal form or diverge?

1. 𝜆𝑥.𝑥𝑥𝑥 is already in normal form
2. (𝜆𝑧.𝑧𝑧)(𝜆𝑦.𝑦𝑦) diverges since the first application to $z$ yields (𝜆𝑦.𝑦𝑦)(𝜆𝑦.𝑦𝑦) which is *omega*
3. (𝜆𝑥.𝑥𝑥𝑥)𝑧 becomes 𝑧𝑧𝑧 -> normal form

## Beta reduce

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
