# Challenge 3 Day 3

Instructions:

1. Fork this Challenge, **make a folder with your [username]-[language] as the folder name** and make any pushes to that repository, then create a pull request.
2. Use any language you prefer.
3. Include a README.md file to show how to run and compile the code.
4. In your own interest comment your code.
5. In your own interest attach Screenshots for your results.
6. Comment on another person's work for positive growth

## Mini Challenge 1

You are given two positive integers `n` and `d`(`n` is given by string fromat). And then, we are playing a `Remove Number Game`:

- 1st turn, we remove a digit from `n`, that the resulting number has at least one `non-zero` digit and is divisible by `d`.
- 2nd turn, we remove a digit from `n`, that the resulting number has at least one `non-zero` digit and is divisible by `d-1`.
- 3rd turn, ................................divisible by `d-2`.
- ith turn, ................................divisible by `d-i+1`.
- And so on. Until `d-i+1` is decreased to 1 or you can not find a way to romove 1 digit from `n` and is divisible by `d-i+1`.

Your task is, determine the maximum possible number of turns you can make.

Still not understand the task? Look at the following examples:

# Examples

For `n = "102045" and d = 4`, the output should be `4`.

```
turn 1: "102045" -> "10204" (remove 5 from n)
                    "10204" is divisible by 4
turn 2: "10204" -> "0204" (remove 1 from n)
                   "204" is divisible by 3
turn 3: "204" -> "20" (remove 4 from n)
                 "20" is divisible by 2
turn 4: "20" -> "2" (remove 0 from n)
                "2" is divisible by 1

Perhaps there are many ways to playing this game.
But the maximum possible number of turns should be 4.
```

For `n = "5555" and d = 3`, the output should be `1`.

Only 1 turn: `"5555"` -> `"555"`(divisible by 3), `"555"` remove any digit `5` will became to `"55"`, but `"55"` is not divisible by `2`. So, after turn 1, the game is over.

For `n = "88" and d = 2`, the output should be `1`.

Only 1 turn: `"88"` -> `"8"`(divisible by 2), `"8"` can not remove digit again.

For `n = "100000" and d = 4`, the output should be `1`.

Note that `"100000"` can only remove digit `0` from it. If we removed digit `1`, `"00000"` is not a valid number.

# Note

- `2 <= n.length <= 15`
- `1 <= d <= 15`



## Mini challenge 2

A number m of the form 10x + y is divisible by 7 if and only if x − 2y is divisible by 7. In other words, subtract twice the last digit from the number formed by the remaining digits. Continue to do this until a number known to be divisible or not by 7 is obtained; you can stop when this number has *at most* 2 digits because you are supposed to know if a number of at most 2 digits is divisible by 7 or not.

The original number is divisible by 7 if and only if the last number obtained using this procedure is divisible by 7.

Examples:

1 - `m = 371 -> 37 − (2×1) -> 37 − 2 = 35` ; thus, since 35 is divisible by 7, 371 is divisible by 7.

The number of steps to get the result is `1`.

2 - `m = 1603 -> 160 - (2 x 3) -> 154 -> 15 - 8 = 7` and 7 is divisible by 7.

3 - `m = 372 -> 37 − (2×2) -> 37 − 4 = 33` ; thus, since 33 is not divisible by 7, 372 is not divisible by 7.

The number of steps to get the result is `1`.

4 - `m = 477557101->47755708->4775554->477547->47740->4774->469->28` and 28 is divisible by 7, so is 477557101.

The number of steps is 7.

# Task:

Your task is to return to the function `seven(m)` (m integer >= 0) an array (or a pair, depending on the language) of numbers, the first being the *last* number `m` with at most 2 digits obtained by your function (this last `m` will be divisible or not by 7), the second one being the number of steps to get the result.

## Forth Note:

Return on the stack `number-of-steps, last-number-m-with-at-most-2-digits`

## Examples:

```
seven(371) should return [35, 1]
seven(1603) should return [7, 2]
seven(477557101) should return [28, 7]
```

## Minichallenge 3

It's been a tough week at work and you are stuggling to get out of bed in the morning.

While waiting at the bus stop you realise that if you could time your arrival to the nearest minute you could get valuable extra minutes in bed.

There is a bus that goes to your office every 15 minute, the first bus is at `06:00`, and the last bus is at `00:00`.

Given that it takes 5 minutes to walk from your front door to the bus stop, implement a function that when given the curent time will tell you much time is left, before you must leave to catch the next bus.

## Examples

```
"05:00"  =>  55
"10:00"  =>  10
"12:10"  =>  0
"12:11"  =>  14
```

### Notes

1. Return the number of minutes till the next bus
2. Input will be formatted as `HH:MM` (24-hour clock)
3. The input time might be after the buses have stopped running, i.e. after `00:00`



> Happy are those who get no error on their compiles, for theirs is the joy of compilation