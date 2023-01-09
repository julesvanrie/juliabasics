# Control structures

## Conditional execution
```julia
# Example one
if some condition
	some stuff happens
elseif some other condition
	some other stuff happens
elseif still some other condition
	some other stuff happens
else
	even other stuff happens (fallback scenario)
end
```
```julia
# Example two
if something
	some stuff happens
else
  something different happens
  if somethingelse
	  some other stuff happens
  else
      even other stuff happens
  end
  here something can happen
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
while not setended
	play next game
	if difference is two
		setended = true
end
```

### Change execution : **break** and **continue**
`continue`: continue with the next execution (next `i` or next `artists` for examples above)
`break`: break out of the loop and continue afterwards

```julia
total = 0
while less than 7 cards
	take another card
	total += newcard.value
	if total > 21
		break
end
println("You lost")
```


## Functions

Functions deserve a separate note.
