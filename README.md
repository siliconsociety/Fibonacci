# Calculating the Fibonacci Sequence

The Fibonacci sequence is a series of numbers in which each number is the sum of the two preceding ones, typically starting with 0 and 1. It was introduced by the Italian mathematician Leonardo of Pisa, who was also known as Fibonacci, in his 1202 book Liber Abaci. The sequence has since been widely studied due to its unique mathematical properties and its frequent occurrence in nature, art, and architecture.

The Fibonacci sequence begins as follows: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34, ... and continues indefinitely. The nth term of the sequence, denoted as F(n), can be calculated using the following rules:

```
F(0) = 0
F(1) = 1
F(n) = F(n-1) + F(n-2) for n > 1
```

### Code Examples
- Fib Recursion: `/fib_funcs/fib_recursive.py`
- Fib Iteration: `/fib_funcs/fib_iteration.py`
- Fib Generator: `/fib_funcs/fib_generator.py`
- Fib Function Caching: `/fib_funcs/fib_cache.py`
- Fib Matrix Exponentiation: `/fib_funcs/fib_matrix.py`
- Fib Lambda Calculus: `/fib_funcs/fib_lambda_calc.py`

Some interesting properties of the Fibonacci sequence include:

#### Golden Ratio (Phi)
As the sequence progresses, the ratio between consecutive terms approaches the Golden Ratio, approximately 1.6180339887... This number is considered aesthetically pleasing and has been used in art, architecture, and design throughout history.

### Sum of consecutive Fibonacci numbers
The sum of the first n Fibonacci numbers is equal to the (n+2)nd Fibonacci number minus 1. In other words, F(0) + F(1) + F(2) + ... + F(n) = F(n+2) - 1.

### GCD and Fibonacci numbers
The greatest common divisor (GCD) of two Fibonacci numbers, F(m) and F(n), is another Fibonacci number, specifically F(GCD(m, n)).

### Periodicity modulo m
The Fibonacci sequence exhibits periodicity when taken modulo m for any positive integer m. This is known as Pisano periods.

### Fibonacci numbers and Lucas numbers
The Lucas numbers are a related sequence with a similar recursive definition, but they start with 2 and 1 instead of 0 and 1. Many identities and properties connect the Fibonacci and Lucas numbers.

### Fibonacci numbers in nature
The Fibonacci sequence is frequently found in nature, including the arrangement of leaves on a stem, the branching of trees, the number of petals on flowers, and the spiral patterns of seeds in fruits.

### Recursive and iterative algorithms
Although the Fibonacci sequence is defined recursively, it can be computed using both recursive and iterative methods. The recursive method has a higher time complexity, while the iterative method is more efficient and avoids potential issues with stack overflow.

### Matrix exponentiation and closed-form expression
The Fibonacci sequence can be calculated using matrix exponentiation, which allows for a more efficient computation of the nth term. Additionally, the closed-form expression for the nth Fibonacci number, known as Binet's formula, relies on the Golden Ratio and its conjugate.

## Recursion Implementation: Lambda Calculus Y-combinator
The Y-combinator is a fixed-point combinator in Lambda Calculus that allows for the definition of recursive functions. As such it does **not** rely on the precondition runtime support for recursion. In the code example, the recurse function is an implementation of the Y-combinator and thus implements recursion from scratch. This code is written purely for academic study and not intended to be used in production.

Let's break down the code step by step to understand how the Y-combinator is used to define the Fibonacci function in a recursive manner:

- recurse(tree) is a higher-order function that takes a function tree as input. Inside recurse, there are two other functions defined: limb and branch.

- limb(left) takes a function left and returns a new function that takes a function right as input. This returned function applies left to itself and then applies the resulting function to right.

- branch(leaf) takes a function leaf and returns the result of applying tree to limb(leaf).

- recurse returns the result of applying branch to itself: branch(branch).

- fib_lambda_calc(n) is a wrapper function for calculating the nth Fibonacci number using the Y-combinator. Inside fib_lambda_calc, a worker function fib_worker is defined.

- fib_worker(fib) takes a function fib and returns a lambda function that calculates the nth Fibonacci number. If the input a is less than or equal to 2, it returns 1. Otherwise, it calculates fib(a - 1) + fib(a - 2).

- Finally, recurse(fib_worker) is called, which results in the Y-combinator being applied to the fib_worker. The resulting function is then called with the input n, giving the nth Fibonacci number.

The main idea behind the Y-combinator is that it enables recursion without explicit self-reference. Instead, the recursion is achieved by applying the Y-combinator to a worker function (like fib_worker), which defines the core operation. The Y-combinator effectively "ties the knot" and allows the worker function to refer to itself indirectly.
