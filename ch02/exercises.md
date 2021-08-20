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

   Both will evaluate to 100

3. `400 - 37`

   `(-) 37 400`

   The first expression will evaluate to `363` while the second will evaluate to `-363`

4. `100 'div' 3`

   `100 / 3`

   The first expression will do integral division i.e division of integers therefore it will return `33`.

   The second expression will do fractional division and will return something like `33.333...`

5. `2 * 5 + 18`

   `2 * (5 + 18)`

   Because of the higher precedence of multiplication, in the first expression multiplication will be evaluated first.

   In the second expression addition will be evaluated first because of the parenthization. The results will be different.

### More fun with functions

Here is a bit of code as it might be entered into a source file.
Remember that when you write code in a source file, the order
is unimportant, but when writing code directly into the REPL
the order does matter. Given that, look at this code and rewrite
it such that it could be evaluated in the REPL (remember: you
may need let when entering it directly into the REPL). Be sure
to enter your code into the REPL to make sure it evaluates
correctly

```
z = 7

x = y ^ 2

waxOn = x * 5

y = z + 8

```

In the REPL. Am not using `let` because in GHC greater than 8. Its not really required though it does no harm to precede expressions with let

```
z = 7

y = z + 8  -- 15

x = y ^ 2  -- 225

waxOn = x * 5 -- 1125

```

1. Now you have a value called waxOn in your REPL. What do
   you think will happen if you enter:

```
> 10 + waxOn

> 1135

> (+10) waxOn

> 1135

> (-) 15 waxOn

> -1110

> (-) waxOn 15

> 1110

```

2. Earlier we looked at a function called triple. While your
   REPL has waxOn in session, re-enter the triple function at
   the prompt:

   `triple x = x * 3`

3. Now, what will happen if we enter this at our GHCi prompt?
   What do you think will happen first, considering what role
   waxOn is playing in this function call? Then enter it, see
   what does happen, and check your understanding:

   `triple waxOn`

   The argument `waxOn` will be bound to the parameter `x` of the triple function and the function will be applied to waxOn

   ```
   > triple waxOn

   > 3375

   ```

   For remaining exercises, see [where.hs](https://github.com/samtechie/haskellbook/blob/main/ch02/where.hs)
