# Arrays

## Exercise 1

```julia
myarray = [5, 6, 8, 9, 4, 3, 4, 6, 7, 1]
reversedarray = myarray[end:-1:begin]
```

## Exercise 1

```julia
push!(myarray, 15)
pushfirst!(reversedarray, 15)
```

## Exercise 3

```julia
alltogether = myarray[:]
append!(alltogether, reversedarray)
```

## Exercise 4

```julia
function checksymmetry(anarray)
  anarray == anarray[end:-1:begin]
end

checksymmetry(alltogether)
```

## Exercise 5

```julia
english = ["one", "two", "three", "four", "five", "six", "seven", "eight", "nine", "ten"]
while true
  print("Give me a number: ")
  answer = parse(Int64, readline())
  println("$(answer) is $(english[answer]) in English")
end
```


## Exercise 6

```julia
myarray = [5, 6, 8, 9, 4, 3, 4, 6, 7, 1]

function surfaces(diameters)
  surfaces = []
  for d in diameters
    push!(surfaces, pi * (d/2)^2)
  end
  return surfaces
end

surfaces(myarray)

function printsurfaces(diameters)
  mysurfaces = surfaces(diameters)
  for i in 1:length(diameters)
    println("The surface of a circle with diameter $(diameters[i]) is $(round(mysurfaces[i], digits=2))")
  end
end

printsurfaces(myarray)
```
