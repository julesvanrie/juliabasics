# Text

## Exercise 1

Create variables:
- `first` with a first name (e.g. 'John')
- `last` with a last name (e.g. 'Doe')

Concatenate the variables, so that the result is "John Doe" (with a space in between)
<details>
  <summary>Hint</summary>

  - `"more" * "text"` returns `"moretext"`.
  - Now, how do you fit a space in between?

</details><br>

## Exercise 2

Using the variables you created before, print "My name is John Doe" using string concatenation
<details>
  <summary>Hint</summary>

  ```julia
  sometext = "world"
  println("Hello $(sometext)!")    # prints "Hello world!"
  ```
</details><br>


## Exercise 3

Print a line consisting of 30 minus signs (something like: - - - - - - - -)
<details>
  <summary>Hint</summary>

  `"a" ^ 5` returns  `"aaaaa"`.

</details><br>

## Exercise 4

Using the variables you created, print the name, preceded by the inital of the first name ("J. Doe")
<details>
  <summary>Hint</summary>

  Think of square bracket indexing (`sometext[1]`)

</details><br>

## Exercise 5

Create a variable `strangetext = "aCeogneggrzaht2utloaetziwojnus/!3 wYyoxui  s2onlkvzeed[ di;tt"`.
- There's a message hidden in the text.
- Print every other letter (starting from the second letter; letters 2, 4, 6, 8 ...)<details>
  <summary>Hint</summary>

  Think of square bracket indexing with `start:step:end`

</details><br>

- Do not count the number of letters yourself, but let Julia do the heavy work.<details>
  <summary>Hint</summary>

  `length`

</details><br>
