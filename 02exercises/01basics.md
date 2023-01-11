# Basics exercises

## Numeric calculations

- Create a variable `myvar`, and store a number without decimals in it.

- What is the type of `myvar`?<details>
  <summary>Hint</summary>

  `typeof(myvar)` to check in the REPL

  </details><br>

- Do the same with a number with decimals in it. What type is it?

- Calculate this variable to the power of 2

- Calculate this variable to the power of 60<details>

  <summary>Hint</summary>

  `2 ^ 3` returns `8`

  </details></br>

- Calculate the square root of `myvar`<details>
  <summary>Hint</summary>

  `sqrt(9)` returns `3`

  </details><br>

## Logical operations

What is the result  (`true` or `false` or something else) of:

1. `2 >= 2`
2. `3 > 2 & 2 == 1`
3. `3 > 2 | 2 == 1`
4. `3 > 2 & 2 != 1`
5. `!(3 > 2)`
6. `!2 == 1`
7. `3 > 2 & 2 = 1`
8. `true & false & true`
9. `true & false | true`
10. `true & true | false`
11. `true & (false | true)`
12. `false & !false | true`

<details>

<summary>Answers</summary>

1. `true`
2. `false`
3. `true`
4. `true`
5. `false`
6. Error, this doesn't work. You need parenthesis: `!(2 == 1)`.
7. Error, this doesn't work. In the second condtion you needed `==` instead of `=` to check for equality.
8. `false`
9. `true`
10. `true`
11. `true`
12. `true`

  </details></br>
