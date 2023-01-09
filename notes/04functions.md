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

function move(person)  # person is the "parameter" of this function
	distance = 10   # This distance is now different from the outside one
	person.position += distance   # person moves 10 forward
end

pers = Person()    # Creating a Person (whatever that may be)
move(pers)      # Calling move with "argument" pers

# Names inside the function are independent of names outside.
# Once I pass pers as argument, inside the function,
# it goes by the name person

# I can also do this
person = Person()
move(person)

# Or
john = Person()
move(John)
```
