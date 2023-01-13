# Text

## Exercise 1

```julia
julia>
julia> first = "John"
"John"

julia> last = "Doe"
"Doe"

julia> first * " " * last
"John Doe"
```

## Exercise 2

```julia
julia> println("My name is $(first) $(last)")
My name is John Doe
```

## Exercise 3

```julia
julia> println("-" ^ 30)
------------------------------
```

## Exercise 4

```julia
julia> println("$(first[1]). $(last)")
J. Doe
```

## Exercise 5

```julia
julia> strangetext = "aCeogneggrzaht2utloaetziwojnus/!3 wYyoxui  s2onlkvzeed[ di;tt"
"aCeogneggrzaht2utloaetziwojnus/!3 wYyoxui  s2onlkvzeed[ di;tt"

julia> println(strangetext[2:2:length(strangetext)])
Congratulations! You solved it
```
