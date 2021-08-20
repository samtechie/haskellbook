## Chapter Exercises

### Parenthesization

Given what we know about the precedence of (\*), (+), and (^),
how can we parenthesize the following expressions more explicitly
without changing their results? Put together an answer
you think is correct, then test in the GHCi REPL.

1. `2 + 2 * 3 - 1`

   `2 + (2 * 3) - 1`

2. `(^) 10 $ 1 + 1`

   `(10^) $ (1 + 1)`

3. `2 ^ 2 * 4 ^ 5 + 1`

   `(2 ^ 2 )* (4 ^ 5) + 1`

### Equivalent expressions

Which of the following pairs of expressions will return the
same result when evaluated? Try to reason them out by reading
the code and then enter them into the REPL to check your
work:

1. `1 + 1`

   `2`

   Both will evaluate to 2

2. `10 ^ 2`

   `10 + 9 * 10`

   Both will evaluate to a hundred
