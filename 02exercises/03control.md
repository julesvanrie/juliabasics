# Control structures

## Exercise 1

For the European elections, one has to be 18 to be able to vote, but one must be 21 to be a candidate for the elections.

Write a control structure that takes a variable `age`, and that prints out if a person with that age can vote, can be a candidate, or is still too young.

<details>
  <summary>Hint</summary>

  The order of your `if` and `else` conditions matter. What do you think will happen if you switch the order?

  (If your code didn't work, this is probably what you need to look into.)

</details><br>

## Exercise 2

Create a variable mylongtext as hereunder.
(Multiline strings in Julia are in between triple quotes.)
```julia
mylongtext = """
Stately, plump Buck Mulligan came from the stairhead, bearing a bowl of lather on which a mirror and a razor lay crossed. A yellow dressinggown, ungirdled, was sustained gently behind him on the mild morning air. He held the bowl aloft and intoned:

—Introibo ad altare Dei.

Halted, he peered down the dark winding stairs and called out coarsely:

—Come up, Kinch! Come up, you fearful jesuit!

Solemnly he came forward and mounted the round gunrest. He faced about and blessed gravely thrice the tower, the surrounding land and the awaking mountains. Then, catching sight of Stephen Dedalus, he bent towards him and made rapid crosses in the air, gurgling in his throat and shaking his head. Stephen Dedalus, displeased and sleepy, leaned his arms on the top of the staircase and looked coldly at the shaking gurgling face that blessed him, equine in its length, and at the light untonsured hair, grained and hued like pale oak.
""";
```

- How many vowels are in this piece of text?
- What percentage of the total text is this? (Rounded to 0.1%)

<details>
  <summary>Hint</summary>

  - You will have to loop over every letter in mylongtext
  - Test this code in the REPL: `'c' in "abcd"`
  - Think how you can use this concept to isolate vowels
  - To round the percentage you can use `round(number, digits=x)` with `x` the number of digits you want to keep

</details><br>

<details>
  <summary>Answer</summary>

  The answer should be `271`, which is `29%` of the total length.

</details><br>

<details>
  <summary>Encountering strange rounding?</summary>

  Depending on how you did the rounding to get to a percentage, you might get some strange results:
  ```julia
round(ratio, digits=3)         # 0.291
round(ratio, digits=3) * 100   # 29.099999999999998   Why?
round(100*ratio, digits=1)     # 29.1
```
</details><br>


## Exercise 3

Write a program that:
- Asks the user `What is your question?`
- The user then inputs his question followed by \<ENTER\>
- Prints the user's questions: `Your question was: ` followed by the user's question.
- As you know, a questions ends with a question mark. So, the computer has to say `That's not a question!` to non-questions.
- To any question the computer answers: `Computer says no...`
- Repeats from the start
- The program only stops if the user types any phrase that starts with `I'm going`. So, it stops in case of:
  - `I'm going`
  - `I'm going!`
  - `I'm going now`
But not in case of: `That's it! I'm going`

To read input from the user, you can use this code snippet:
```julia
print("What is your question? ")
answer = r
```

## Exercise 4

Change your previous program, so that it automatically stops if the user does 3 consecutive attempts without asking a question (a question is any input containing a question mark). In that case the computer will say `I have had enough. I need a nap.`


<details>
  <summary>Hint 1</summary>

  For exercise 3 you probably used a `while` loop.

  So you could initiate a counter before the loop, increase it each time the user does not ask a question, and then check that counter in the while loop.
</details><br>

<details>
  <summary>Second part</summary>

  The computer should only stop after 3 **consecutive** attemps. So if the user has entered a non-question twice, and then enters a question, and then again a non-question, the computer should **not** exit.

  Does your program work this way?
</details><br>


<details>
  <summary>Hint 2</summary>

  You initiated a counter, and increase it after every non-question. So what should happen with this counter when the user enters a question?

</details><br>
