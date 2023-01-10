# Recursion and the stack

## Basics

- Recursive function are functions that basically call themselves.
- Can be used to solve many problems
- The idea is to solve a problem by reducing it to the some problem but smaller

Let's look at an example to make it easier

## Example: factorial function

A classic example is the mathematical factorial function, notated as *n!*. It is the product of all positive integers smaller than or equal to *n*. The factorial of 0 is defined as 1.

For example:
- *3! = 3 &#183; 2 &#183; 1*
- *4! = 4 &#183; 3 &#183; 2 &#183; 1*
- *5! = 5 &#183; 4 &#183; 3 &#183; 2 &#183; 1*

From this definition one can see that for example:
- *5! = 5 &#183; 4!*
- *4! = 4 &#183; 3!*

Or more general

- *n! = n &#183; (n-1)!*
- *0! = 1*

And, that is a typical example of a recursive function: the function for *n* depends on calling the same function for *n - 1*.

So, a recursive function for factorial in Julia is:

```julia
function fact(n)
  if n == 0
    return 1
  else
    return n * fact(n - 1)
  end
end
```

## Advantages and pitfalls

Recursive functions can be easy to code. (The above `fact` function is very short.) But they can be inefficient, and can even result in a so-called 'stack overflow'.

## The stack

Whenever a function is called, it is a added to the so-called stack. You can almost literally see it as a stack. You will also see it referred to as *call stack*, *execution stack*, *program stack*, ... Let's try to explain this intuitively (the real process is more complex).

Imagine the following imaginary program:

```julia
function function3(c)
  return c + 3
end

function function2(b)
  return function3(b+2)
end

function function1(a)
  return function2(a+1)
end

x = 2
function1(x)
```

- A program always starts from its main part.
- When the main program starts, it calls `function1`, passing *2* as argument.
- `function1` calls `function2` passing *a+1 = 2+1 = 3* as argument.
- `function2` calls `function3` passing *b+2 = 3+2 = 5* as argument.
- Now we have reached the end of these series of calls: `function3` does not call any other functions, but calculates *c+3 = 5+3 = 8* and returns it to `function2`. Once `function3` has done its work, it can be removed from the stack again.
- Now that `function3` has returned, `function2` can finalize its calculation. It returns *8* to `function1`. `function2`, now that it has done its work, can be removed from the stack again.
- Now that `function2` has returned, function1 can finalize its calculation. It returns *8* to the main program. `function1`, now that it has done its work, can be removed from the stack again.


You can see the stack as a pile of work that needs to be done by the computer for this program. The pile builds up, and then gets reduced again.

On the stack, each time a couple of things are added:
- the function
- the local variables of the function:
  - 'bound' values: the function's parameters
  - 'free' values: other values
- a reference to its immediate outside environment (from where the function was called: for `function2` this is to the environment of `function1`, for `function1` this is the main environment)

| Start       | | One call      | | Two calls     | | Three calls   |
| ----------- | | ------------- | | ------------- | | ------------- |
| main    x=2 | | main      x=2 | | main      x=2 | | main      x=2 |
|             | | function1 a=2 | | function1 a=2 | | function1 a=2 |
|             | |               | | function2 b=3 | | function2 b=3 |
|             | |               | |               | | function3 c=5 |


## Alternatives

Fortunately, these functions can often be rewritten using loops, and/or some storage of previous result. These solutions are often less straighforward to code. We will do this for the factorial function in the exercises.