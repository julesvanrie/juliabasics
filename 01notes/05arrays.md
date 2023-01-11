# Arrays

## What?
A collection of elements, in this case a sequence, meaning that the elements have an order, and we will refer to them by their place in the collection


## Creating arrays
Upon creation, Julia detects the most specific abstract type that covers all elements.
```julia
intarray = [10, 20, 30, 40]       # Array of type Int64

floatarray = [10, 20.1, 30, 40]   # Array of type Float64

anyarray = ["some text", 1, 2.5]  # Array of type Any

emptyarray = []                   # Array of type Any (empty)

emptyintarray = Int64[]           # Array of type Int64 (empty)

intarray[1] = 2.1                 # Error: float won't fit into Int64[]
```

## Indexing
```julia
newarray = [10, 20, 30, 40]       # Array of type Int64

newarray[2]
>>> 20

newarray[2:3]
>>> 20
    30

newarray[1:2:4]
>>> 10
    30
```

# Adding and removing elements
Functions whose name ends in `'!'` change the original array!

This can lead to unintendent consequences. Think of making a copy first if you want to avoid this.

```julia
longerarray = push!(newarray, 50)
>>> 10
    20
    30
    40
    50

newarray        # push! has also changed the original array
>>> 10
    20
    30
    40
    50
```
```julia
pop!(newarray)  # Returns last element and removes it
>>> 50

newarray        # newarray has changed !
>>> 10
    20
    30
    40

# pushfirst!  and popfirst!  >> same, but from the start of the array

# Appending an array to an array
append!(newarray, [100, 200])    # newarray has changed
>>> 10
    20
    30
    40
    100
    200
```

If you want to keep the original array, first make a copy and work on that copy
```julia
copyarray = newarray[:]

# Careful when you reference an array
a = [1, 2, 3]
b = a                # b points to the same array as a

b[2] = 200           # So, when I change b, I also change a

a
>>> 1
    200
    3
```

This results from the fact that arrays are "mutable".
Note: strings are not mutable. You would not be able to do this:
```julia
text = "sometext"
text[1] = "1"   # This will not work
```

Careful when you are working with arrays of arrays (or other type of collections). To make a real copy of every subarray, you need to use `deepcopy(myarray)`
