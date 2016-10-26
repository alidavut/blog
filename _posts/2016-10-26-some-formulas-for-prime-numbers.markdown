---
title:  "Some Formulas for Prime Numbers"
description: Some simple formulas which gives always a primer number
date: 2016-10-26 14:56:00
pid: 3
---

[TL;DR](#the-formula-and-the-example) In 2005 or 2006, I don't remember well. I was being prepared for the university exam, was thought the most important exam for the students in Turkey then. The only thing I knew in math was simple rational numbers by then. I was very lazy in the past.

In this period, my interest about math was increasing day by day. I was spending lots of time to get qualified for an engineering class. (In the end I graduated as a computer engineer.)

Anyway. One day we were talking about general things about math and the teacher said that "Prime numbers is the one of the most interesting math problems. There is no correct function which always gives prime number as a result.". After I heard this, my interest were in the top level about prime number, I had to work on it.

After the class, I went home and started to try finding a relationship between the numbers. I spent a few weeks with the prime number. As a result I couldn't find anything correct :). But I found a few interesting formulas which gives prime numbers with some conditions.

I wanted to share these functions because someone may get interested and find a relationship between the formulas.

By the way, I don't know anyone already shared this before. Forgive me I didn't investigated enough.

### The Formula and The Example

Lets say 'a' is a prime number and 'n' is a positive number less than 'a'. If we give 'a' as one of [2, 3, 5, 11, 17, 41], the function always returns a prime number.

**The formula is:** \\(n^2 - n + a\\)

As you see it's very simple but it made me very excited then.

Here is the example javascript code which calculates whether the formula is correct which given prime number until 100.

As a result these formulas work with the given conditions.

```
n ^ 2 - n + 2 (works for n = 1)
n ^ 2 - n + 3 (works for n = 1, 2)
n ^ 2 - n + 5 (works for n = 1, 2, 3, 4)
n ^ 2 - n + 11 (works for n = 1, 2, ... 10)
n ^ 2 - n + 17 (works for n = 1, 2, ... 16)
n ^ 2 - n + 41 (works for n = 1, 2, ... 40)
```

<script async src="//jsfiddle.net/5b317fad/3/embed/js,result/dark/?fontColor=fff"></script>
