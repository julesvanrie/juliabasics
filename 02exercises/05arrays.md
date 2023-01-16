# Arrays

## Exercise 1

Create an array `myarray` of 10 numbers.

Created a new array `reversedarray` with the same 10 numbers, but in reversed order.

## Exercise 2

Add a new number to the end of `myarray`.

Add the same number to `reversedarray`, but at the beginning, so that `reversedarray` is still the same as `myarray` but in reversed order.

## Exercise 3

Create a new array `alltogether` taking all the numbers of `myarray` followed by all the numbers of `reversedarray`.

Make sure `myarray` is still the same array as before (with 11 elements).

## Exercise 4

Write a function that checks if an array is symmetric. Test it on `alltogether`.

<details>
  <summary>Hint</summary>

  Your function body can be as short as one line. Think of how you made the reverse of an array.
</details><br>

## Exercise 5

Write a program that asks a number (integer from 1 to 10) from the user, and prints out the number followed by the English word as in the example hereunder.

Do **not** use a long `if - elseif` construction.

For example:
```
Give me a number: 5
5 is five in English
```

To read input from the user, you can use this code snippet:
```julia
print("Give me a number: ")
answer = readline()
```

<details>
  <summary>Hint</summary>

  You can store the numbers in English in an array.

  For the printing, use string concatenation. For example:

  ```julia
  number = 7
  println("I am $(number)")    # Prints "I am 7"
  ```
</details><br>

## Exercise 6

Start with your `myarray` from exercise 1 (10 numbers).

Create a function that takes an array as argument, and returns a new array containing the surfaces of circles with diameters as defined in the argument.

Example usage: `surfaces([1,2,10])` returns an array `[3.14, 12.68, 314]` (approximately, do not worry about rounding errors).

Create another function that takes an array as argument and prints for each diameter in the diameter and the surface.

Example usage:  (do not worry about rounding errors)
```julia
printsurfaces([1,2,10])
>>> The surface of a circle with diameter 1 is 3.14.
    The surface of a circle with diameter 2 is 12.68.
    The surface of a circle with diameter 10 is 314.
```

Test the functions you made on your `myarray`.

<details>
  <summary>Hint</summary>

  You probably guessed that you have to loop simultaneously over two (same-sized) arrays.

  Previously you might have looped over an array like this:
  ```julia
  for diameter in myarray
    println(diameter)
  end
  ```
  Alternatively you can loop over the array using the index:
  ```julia
  for i in 1:3
    println(myarray[i])
  end
  ```
  Think of how you can use this to loop over the two arrays at the same time.

</details><br>


Now test it again on the array `alltogether` from exercise 4.

Does your function print out 22 lines? Congratulations! If not, change your code so it does.
