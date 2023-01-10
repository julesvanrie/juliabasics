# Recursion

## Exercise 1

A classic example for recursive function is the generation of [Fibonacci numbers](https://en.wikipedia.org/wiki/Fibonacci_number), which have a wide range of applications.

They are defined as follows:
- F<sub>0</sub> = 0
- F<sub>1</sub> = 1
- F<sub>n</sub> = F<sub>n-1</sub> + F<sub>n-2</sub>

So, some examples:
- F<sub>2</sub> = F<sub>1</sub> + F<sub>0</sub> = 1 + 0 = 1
- F<sub>3</sub> = F<sub>2</sub> + F<sub>1</sub> = 1 + 1 = 2
- F<sub>4</sub> = F<sub>3</sub> + F<sub>2</sub> = 2 + 1 = 3
- F<sub>5</sub> = F<sub>4</sub> + F<sub>3</sub> = 3 + 2 = 5
- F<sub>6</sub> = F<sub>5</sub> + F<sub>4</sub> = 5 + 3 = 8

These numbers seem to increase slowly, but F<sub>6</sub> amounts already to 4181!

Implement a recursive function `fib(n)` to calculate the n-th Fibonacci number.

Test your function with `fib(19)`. Does it return 4181?

<details>
  <summary>Hint</summary>

  Your function keeps calling itself without ever giving a result?

  Recursive functions always need a base case scenario. Have you implemented that "starting" scenario inside the `fib` function?

</details><br>

## Exercise 2

Run the following code. What do you notice?

```julia
for i in 20:46
  println("fib($(i)) = $(fib(i))")
end
```

<details>
  <summary>Answer</summary>

  It takes more and more time.
  Think a second why? How many calculations are needed?

</details><br>

  <details>
    <summary>Explanation</summary>

  Step 1:
  - F<sub>10</sub> asks to calculate F<sub>9</sub> and F<sub>8</sub>

  Step 2:
  - F<sub>9</sub> asks to calculate F<sub>8</sub> and F<sub>7</sub>
  - F<sub>8</sub> asks to calculate F<sub>7</sub> and F<sub>6</sub>

  Step 3:

  - F<sub>8</sub> asks to calculate F<sub>7</sub> and F<sub>6</sub>
  - F<sub>7</sub> asks to calculate F<sub>6</sub> and F<sub>5</sub>
  - F<sub>7</sub> asks to calculate F<sub>6</sub> and F<sub>5</sub>
  - F<sub>6</sub> asks to calculate F<sub>5</sub> and F<sub>4</sub>

  The repetition in step 3 (second and third bullet) is not a typo. This same calculation is happening twice.

  This branching repeats and repeats again, until you get 2^n branches. This will take forever as n gets larger.

  </details><br>


## Exercise 3

Knowing what we know now, let's think of another way to implement this function more efficiently.

Recursive functions can be easy to code. (Your above `fib` function should not be longer than a few lines.) But they can be inefficient, and can even result in a so-called 'stack overflow'. (Look it up, or ask for explanation.)

Fortunately, these functions can often be rewritten using loops, and/or some storage of previous result.

Let's try this with the factorial function, notated as *n!*. This function will remind you of the Fibonacci numbers, but it is a bit simpler:

- *n! = n &#183; (n-1)!*
- *0! = 1*

So, a recursive function for factorial is:

```julia
function fact(n)
  if n == 0
    return 1
  else
    return n * fact(n - 1)
  end
end
```

Print `fact(n)` for n from 1 to 24. Something strange happens. Do you know why? (Do not worry about this too much. It is optional. Interesting, but not essential for the next part.)

<details>
  <summary>Answer</summary>

  Remember, integers use 64 bits by default. And they are signed. So one bit is used for the sign. So strange things happen at the edges.

  Compare `2^63` with `2^63 - 1`.

  Compare `fact(20)` with `2^63 - 1`.

  So if you would multiple `fact(20)` with 63 to get `fact(21)` you are what we call "overflowing". An Int64 cannnot capture such huge numbers.

</details><br>

## Exercise 4

Let's try to rewrite `fact(n)` as a function without recursion, but using loops.

<details>
  <summary>Answer</summary>

```julia
function fact_loop(n)
  result = 1
  for i in 1:n
    result *= i
  end
  return result
end
```

Mind, this would still have the same overflowing problem as the previous solution.

</details><br>

## Exercise 5

Now, finally, try to rewrite `fib(n)` (the Fibonacci numbers from the start) as a function without recursion, but using loops.

You will want to make an array for this one.

Think a bit about how you would solve it. If you get stuck, have a look at the solution, and try to understand.

<details>
  <summary>Answer</summary>

```julia
fib_numbers = [1, 1]
function fib_loop(n)
  if n == 0
    return 0
  end
  if n > length(fib_numbers)
    for i in length(fib_numbers):n-1
      push!(fib_numbers, fib_numbers[i] + fib_numbers[i-1])
    end
  end
  return fib_numbers[n]
end
```

You will notice that it is more difficult to write out (or understand) this solution than the recursive version.

But run the following code. It's the same as before (Fibonacci numbers up to 46)), but compare the speed to the previous version.

```julia
for i in 20:46
  println("fib_loop($(i)) = $(fib_loop(i))")
end
```

</details><br>
