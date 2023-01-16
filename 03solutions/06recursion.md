# Recursion

## Exercise 1

```julia
function fib(n)
  if n == 0
    return 0
  end
  if n == 1
    return 1
  end
  return fib(n-1) + fib(n-2)
end
```

## Exercise 3

```julia
for i in 1:24
  println(fact(i))
end
```

## Exercise 4

```julia
function fact(n)
  result = 1
  for i in 1:n
    result = result * i
  end
  return result
end
```

## Exercise 5

```julia
function fib_loop(n)
  # We create an array in which we create the Fibonacci numbers
  # that we have calculated
  fib_numbers = [1, 1]
  if n == 0       # Just in case someone asks the Fibonacci number for 0
    return 0
  end
  # If we haven't calculated the number before, let's calculate it.
  if n > length(fib_numbers)
    # We start with the first Fibonacci number that we haven't calculated yet
    # and loop up to the number that we're interested in
    for i in length(fib_numbers):n-1
      # Calculate the Fibonacci number for i
      fib_i = fib_numbers[i] + fib_numbers[i-1]
      # And add it to the array in which we store the numbers
      push!(fib_numbers, fib_i)
    end
  end
  return fib_numbers[n]
end
```
