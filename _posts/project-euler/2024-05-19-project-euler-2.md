---
title:  "Project Euler Problem 2: Even Fibonacci numbers"
categories: csmath
tags: project-euler
permalink: /project-euler/2/
---

[Problem 2](https://projecteuler.net/problem=1) asks us to calculate the fibonacci numbers under 4.000.000, and calculate the sum of the even ones.
The fibonacci sequence is a sequence of numbers where each number is the sum of the two preceding ones, usually starting with 0 and 1, but in this case the problem has us start with 1 and 2.

A fibonacci calculator is a nice exercise given to students to introduce them to recursion, but in this case, we can solve it using a simple loop.
I will create 2 variables holding the last two numbers of the sequence, and a variable to hold the sum of the even numbers.
I will then iterate over the sequence, adding the last two numbers to get the next one, and checking if it is even to add it to the sum.

```python
a = 1
b = 2
s = 2 # 2 is the first even number in the sequence and we already added it

while a + b < 4000000:
    tmp = a + b
    a = b
    b = tmp

    s += tmp if tmp % 2 == 0 else 0

print(s)
```

You can find all my solutions in my <a href="https://github.com/frank20a/project-euler" target="_blank">GitHub Repository</a>!.

[Previous problem](/project-euler/1/){: .btn .btn--danger}
[Next problem](/project-euler/3/){: .btn .btn--success}
