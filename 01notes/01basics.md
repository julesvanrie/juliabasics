# The very basics

## Expressions and statements

### Expressions

```julia
4 * 2
a + 2
a + b
max(2, 4)
```

### Statements
```julia
myvariable = 5
println("some text")
result = a + 2
```

## Variables
- Use meaningful names (not too long, not too short)
- Can be typed or not (typing can improve efficiency in Julia)
- Variables have scope (will be discussed later)

## Style
- spaces around `=`
- indentation: 4 spaces (use tab key)
- variable and functions: lowercase, avoid underscores `myvariable`, `myfunction`
- Types and Modules: UpperCamelCase: `MyType`, `MyModule`

## Basic data types

### Type system
- Julia uses a hierarchical type system
- Using abstract types and concrete types
- The 'top' abstract type is `Any`, so everything is an `Any`
- Intermediary abstract types are for example `Integer` or `Float`
- And finally we have concrete types, like `Int64` or `Int8`
- Typing (= defining which type a variable has) is not required in Julia, but can improve efficiency (speed, storage space)

### Main numeric types

```julia
# Int64 is the default for Integers
typeof(2)
>>> Int64
typeof(-1)
>>> Int64


# Float64 is the default for Floats
typeof(2.1)
>>> Float64
typeof(2.0)
>>> Float64
# Alternative float notation
1.5e-3 # for 0.0015
1.e6   # for 1 000 000
```

### Booleans

```julia
true
false

# Logical operators
cond1 & cond2  # 'and'
cond1 | cond2  # 'or'
!cond1         # 'not'

# Short-circuit operators: depending on cond1, cond2 is not evaluated
cond1 && cond2  # 'and': if cond1 is false, cond2 is not evaluated
cond1 || cond2  # 'or':  if cond1 is true, cond2 is not evaluated

# Writing conditions (equality requires double ==)
2 == 4    # 'equal' >>> false
2 != 4    # 'not equal' >>> true
a == b
2 < 3
2 >= 1
```


### Main text types

These merit a separate note.
