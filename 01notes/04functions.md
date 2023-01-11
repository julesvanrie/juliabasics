# Functions

## Basics
- Break down code in small easier pieces
- Avoid repetition (DRY)
- Definition before calling
- Separate scope: variables outside are not know
- Only way in for outside data is through arguments (one exception global variables, see later)
- Only way out is through a return

## Simple example
```julia
function distmiles(dist)
	result = dist / 1.6
	return result
end

distancemiles = distmiles(distance)
# Distance goes in through argument
# Result comes out through the return
```
## Return keyword is in some cases optional

Julia returns automatically the last expression. The previous function could be rewritten as:
```julia
function distmiles(dist)
	result = dist / 1.6
    result
end

# or even shorter
function distmiles(dist)
	dist / 1.6
end

# or on one line
distmiles = (dist) -> dist / 1.6
```

## Second example (example of scope)
```julia
distance = 200

function move(position)       # position is the "parameter" of this function
	position += distance      # moves 200 (based on global variable distance = 200)
    println(position)
end

pos = 1000
move(pos)                     # Calling move with "argument" pos
# >>> 1200

# Names inside the function are independent of names outside.
# Once I pass pos as argument, inside the function, it goes by the name position,
# because that is how we defined the function.

# I can also do this: use the same name as in the function definition
position = 2000
move(position)
# >>> 2200

# Or use a completely unrelated name
x = 3000
move(x)
# >>> 3200
```

If we define a local variable distance, this variable will be used.
We say that the local variable distance has "shadowed" the global variable
```julia
distance = 200

function move(position)       # person is the "parameter" of this function
	distance = 10             # This distance is now different from the outside one
	position += distance      # moves 10 (based on local variable distance)
    println(position)
end

pos = 1000
move(pos)                     # Calling move with "argument" pos
# >>> 1010
```
