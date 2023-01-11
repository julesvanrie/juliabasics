# Text types

## Char
Individual letter, not a string
```julia
'a'                  # Defined and represented with single quotes
letter = 'a'
typeof(letter)
>>> Char
```

## String
Text, consisting of one or multiple characters (including whitespace)
```julia
oneword = "text"     # Defined and represented with double quotes
phrase = "This is text"
typeof(phrase)
>>> String
oneletter = "a"      # Using double quotes here, so it is a String, not a Char
typeof(oneletter)
>>> String
```

## Indexing strings
```julia
oneword = "text"
length(oneword)
>>> 4

phrase = "This is text"
phrase[2]            # Indexing is 1-based
>>> 'h'              # This is a Char now, not a string
phrase[2:4]          # Ranges include the end
>>> "his"
"abcdefghi"[1:2:9]   # begin:step:end
>>> "acegi"
```
```julia
for letter in oneword
	print(typeof(letter))
end
>>> CharCharCharChar   # letter has become a Char!
```
The above type of indexing only works with simple text, using only ASCII characters (first 255). With Unicode characters this would result in errors. The above type of indexing looks at byte-level. But in Unicode text, some characters are one byte long, others are 2 or more bytes long, and you risk indexing half a character.

<details>
  <summary>[OPTIONAL] Unicode safe indexing</summary>

```julia
unitext = "A ❤!"
length(unitext)     # Number of characters
>>> 4
sizeof(a)           # Number of bytes
>>> 6

firstindex(unitext)
>>> 1
lastindex(unitext)  # Byte position of last character
>>> 6

nextind(oneword,1)  # Byte position of ' '
>>> 2
nextind(oneword,2)  # Byte position of '❤'
>>> 3
nextind(unitext,3)  # Byte position of '!': 6 because '❤' takes 3 bytes
>>> 6
prevind(oneword,6)  # Byte position of '❤'
>>> 3
```
</details><br>

## String interpolation
```julia
oneword = "text"
newphrase = "This is a piece of $(oneword) now."
println(newphrase)
>>> "This is a piece of text now."

println("2 + 2 = $(2 + 2)")
>>> 2 + 2 = 4
```

## Building a String from Chars
```julia
string('c')
>>> "c"     # This is a string now!

join(['l','e','t','t','e','r','s'])
>>> "letters"
```

## Special characters
```julia
'\t' # Inserts a tab
'\n' # Inserts a newline
println("aaaa\tb\nc\td")
>>> aaaa	b
    c		d
```
