# Control structures

## Conditional execution
```julia
# Example one
if condition1
	println("condition1 was true")
elseif condition2
	println("condition1 was false, condition2 was true")
elseif condition3
	println("condition1 and condition2 were false, condition3 was true")
else
	println("condition1, condition2 and condition3 were false, so fallback scenario")
end
```
```julia
# Example two
if condition1
	println("condition1 was true")
else
  println("condition1 was false")
  if condition2
	  println("condition1 was false, condition2 was true")
  else
      println("condition1 and condition2 were false")
  end
  println("condition1 was false; this prints independent of condition2")
end
```

## Iteration
### **for** : iterate over something finite
```julia
for i in 1:4
	print(i)
end
>>> 1234
```
```julia
arrayofartists = ["John", "Paul", "George", "Ringo"]
for artist in arrayofartists
	println(artist)
end
>>> John
    Paul
    George
    Ringo
```

### **while** : iterate until something happens
```julia
weight = 0
while weight < 3500
  adding = rand(100:100:500)
	weight = weight + adding
	println("adding $(adding) ==> weight becomes $(weight)")
end
println("Loop has ended")
```

### Change execution : **break** and **continue**
`continue`: continue with the next execution (next `i` or next `artists` for examples above)
`break`: break out of the loop and continue afterwards

```julia
weight = 0
while weight < 3500
  adding = rand(100:100:900)
  print("adding $(adding)")
  if adding > 500
    if adding > 800
      println(" ==> That is WAY too heavy ==> I stop completely")
      break
    end
    println(" ==> That is too heavy ==> skipping this one")
    continue
  end
	weight = weight + adding
	println(" ==> That is ok ==> weight becomes $(weight)")
end
println("Loop has ended")
```


## Functions

Functions deserve a separate note.
