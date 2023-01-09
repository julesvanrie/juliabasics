# Control structures

## Exercise one

For the European elections, one has to be 18 to be able to vote, but one must be 21 to be a candidate for the elections.

Write a control structure that takes a variable `age`, and that prints out if a person with that age can vote, can be a candidate, or is still too young.

<details>
  <summary>Hint</summary>

  The order of your `if` and `else` conditions matter. What do you think will happen if you switch the order?

  (If your code didn't work, this is probably what you need to look into.)

</details><br>

## Exercise two

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
