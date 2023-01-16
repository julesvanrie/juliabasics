# Functions


## Exercise 1

### Exercise 1
```julia
function fullname(first, last)
  println(first * " " * last)
end

fullname("John", "Doe")
```

### Exercise 2
```julia
function mynamis(first, last)
  println("My name is $(first) $(last)")
end

mynameis("John", "Doe")
```

### Exercise 4

```julia
function shortname(first, last)
  println("$(first[1]). $(last)")
end

shortname("John", "Doe")
```

## Exercise 2


### Exercise 1
```julia
function fullname(first, last)
  first * " " * last
end

fullname("John", "Doe")
```

### Exercise 2
```julia
function mynamis(first, last)
  "My name is $(first) $(last)"
end

mynameis("John", "Doe")
```

### Exercise 4

```julia
function shortname(first, last)
  "$(first[1]). $(last)"
end

shortname("John", "Doe")
```

## Exercise 3
```julia
function printround(number, digits)
  println(round(number, digits=digits))
end

printround(15.54896, 3)
```

## Exercise 4
```julia
function printround(number)
  println(round(number, digits=precision))
end

precision = 1
printround(15.54896)
```
