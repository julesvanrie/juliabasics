# Functions

## Exercise 1

Take your code from Exercises 1, 2 and/or 4 for the chapter on Text, and "refactor" them into functions where you can pass any first name and last name to the function.

For example, for exercise 1 create a function `fullname` that takes a first and a last name, and prints out the full name. Then you can do for example `fullname("John", "Doe")` and this will print `"John Doe"`.

## Exercise 2

Take the same functions, but instead of printing the name, change the function so that they give the result to the caller.

For example, I can then use the function like this `println(fullname("John", "Doe"))`

## Exercise 3

Create a function `printround` that takes a number and a number of digits and prints the number rounded to the number of digits.

Example usage: `printround(10.1234, 2)` prints `10.12`.

<details>
  <summary>Hint</summary>

  To round a number you can use `round(number, digits=x)` with `x` the number of digits you want to keep.

</details><br>

## Exercise 4

Change the function, so that the user can define the number of digits once in the main program, instead of each time the user uses `printround`.

Example usage:
```julia
precision = 3
printround(10.12345)    # Prints 10.123
```
