---
title:  "Project Euler Problem 3: Largest prime factor"
categories: csmath
tags: project-euler
permalink: /project-euler/3/
---

[Problem 3](https://projecteuler.net/problem=1) introduces us to prime numbers. 
It asks us to find the largest prime factor of the number 600851475143.
First we need an `is_prime` function to check if a number is prime.
A quick search [on the internet](https://geekflare.com/prime-number-in-python/) gave me this simple function with $$ O(\sqrt{n}) $$ complexity.
```python
from math import sqrt

def is_prime(n):
  for i in range(2, int(sqrt(n)) + 1):
    if (n % i) == 0:
      return False
  return True
```

Now we can iterate over the numbers from 2 to the half of the provided number, checking if it is a factor and if it is prime.
```python
n = 600851475143

for i in range(2, n // 2):
  if n % i == 0 and is_prime(i):
    print(i)
```
This will print the prime factors of the number, and the last one will be the largest.

If you are interested, [here](https://en.wikipedia.org/wiki/AKS_primality_test) is the fastest way to check if a number is prime.

You can find all my solutions in my <a href="https://github.com/frank20a/project-euler" target="_blank">GitHub Repository</a>!.

[Previous problem](/project-euler/2/){: .btn .btn--danger}
[Next problem](/project-euler/4/){: .btn .btn--success}
