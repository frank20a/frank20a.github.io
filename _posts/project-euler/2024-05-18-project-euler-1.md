---
title:  "Project Euler Problem 1: Multiples of 3 and 5"
categories: csmath
tags: project-euler
permalink: /project-euler/1/
---

[Project Euler](https://projecteuler.net/) is a website with a collection of challenging computational problems intended to be solved with computer programs. 
In this series, I will work on solving these problems using Python.

[The first problem](https://projecteuler.net/problem=1) starts real easy. 
It asks us to find the sum of all the multiples of 3 or 5 below 1000. 
This can be easily solved using the modulo operator `%`. 
The modulo operator returns the remainder of the euclidean division of the two operands. 
For example, `10 % 3` returns `1` because `10 = 3 * 3 + 1`. 

We can use this operator to check if a number is a multiple of another number. 
If `n % 3 == 0`, then `n` is a multiple of 3.
Then we can iterate over all numbers below 1000 and sum the ones that are multiples of 3 or 5.

```python
s = 0
for i in range(1000):
    if i % 3 == 0 or i % 5 == 0:
        s += i

print(s)
```

You can find all my solutions in my <a href="https://github.com/frank20a/project-euler" target="_blank">GitHub Repository</a>!.

<!-- [Previous problem](/project-euler/0/){: .btn .btn--danger} -->
[Next problem](/project-euler/2/){: .btn .btn--success}
