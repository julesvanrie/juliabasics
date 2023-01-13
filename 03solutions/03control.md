# Control structures

## Exercise 1

```julia
function check(age)
    if age < 18
        println("You will have to wait a bit.")
    elseif age < 21
        println("You can vote, but you can't run as candidate.")
    else
        println("You can run as candidate (and you can vote)")
    end
end

check(16)
check(20)
check(23)
```

or

```julia
function check(age)
  if age < 18
    println("You will have to wait a bit.")
  else
    print("You can vote")
    if age < 21
      println(", but you can't run as candidate.")
    else
      println(" and you can run as candidate.")
    end
  end
end

check(16)
check(20)
check(23)
```


## Exercise 2

```julia
mylongtext = """
Stately, plump Buck Mulligan came from the stairhead, bearing a bowl of lather on which a mirror and a razor lay crossed. A yellow dressinggown, ungirdled, was sustained gently behind him on the mild morning air. He held the bowl aloft and intoned:

—Introibo ad altare Dei.

Halted, he peered down the dark winding stairs and called out coarsely:

—Come up, Kinch! Come up, you fearful jesuit!

Solemnly he came forward and mounted the round gunrest. He faced about and blessed gravely thrice the tower, the surrounding land and the awaking mountains. Then, catching sight of Stephen Dedalus, he bent towards him and made rapid crosses in the air, gurgling in his throat and shaking his head. Stephen Dedalus, displeased and sleepy, leaned his arms on the top of the staircase and looked coldly at the shaking gurgling face that blessed him, equine in its length, and at the light untonsured hair, grained and hued like pale oak.
""";

vowelcount = 0
for c in mylongtext
  if c in "aeiou"
    vowelcount = vowelcount + 1
  end
end

println("Number of vowels: ", vowelcount)
percentage = round((vowelcount / length(mylongtext)) * 100, digits=1)
println("This is $(percentage)% of the text.")
```

## Exercise 3

```julia
while true
  print("What is your question? ")
  answer = readline()
  if length(answer) >= 9
    if answer[1:9] == "I'm going"
      break
    end
  end
  println("Your question was: ", answer)
  if answer[lastindex(answer)] != '?'
    println("That's not a question!")
  else
    println("Computer says no...")
  end
end
```

## Exercise 4

```julia
countattempts = 0
while true
  print("What is your question? ")
  answer = readline()
  if length(answer) >= 9
    if answer[1:9] == "I'm going"
      break
    end
  end
  println("Your question was: ", answer)
  if answer[lastindex(answer)] != '?'
    countattempts = countattempts + 1
    if countattempts >= 3
      println("If you're not asking me questions I'm done.")
      break
    end
    println("That's not a question!")
  else
    println("Computer says no...")
    countattempts = 0
  end
end
```
