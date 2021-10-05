# Control Flow

## Overview

Sometimes we want to go with option A, and other times option B.  That's where `if` statements come in - we can choose which path we want based on some condition.

## If Statements

`if` statements allow us to conditionally execute some code based on a condition.  There are also optional paths for other conditions (`else if`) as well as an "otherwise" action (`else`).

In the example below, we will `eatCheezburger` if we can, as determined by the boolean variable.  If we cannot, we will `eatVeggieburger`.

```js
let iCanHasCheezburger = true;
if(iCanHasCheezburger) {
    eatCheezburger();
}
else {
    eatVeggieburger();
}
```

Let's take a look at an example with `else if`.

```js
let age = 18;

if(age < 16) {
    console.log("You cannot drive or drink.");
}
else if (age < 21) {
    console.log("You cannot drink.");
}
else {
    console.log("You can drink and drive, but please not at the same time!");
}
```

This example uses comparison operators to determine if something is `true` or `false`.  `age < 16` will either be `true` or `false` based on the age variable we set.  These operators are described in the next section.

## Comparison Operators

You can use logical operators to determine if a condition is true or false.

| Operator  | Description                                          |
| --------- | ---------------------------------------------------- |
| ===       | Strict equality.  Example: `2 === 2` (true).         |
| ==        | Loose equality.  Example: `"2" == 2` (true).         |
| <         | Less than.  Example: `3 < 2` (false).                |
| <=        | Less than or equal to.  Example: `3 <= 3` (true).    |
| >         | Greater than.  Example: `3 > 2` (true).              |
| >=        | Greater than or equal to.  Example: `3 >= 3` (true). |
| &&        | And.  Example: `3 > 2 && 3 < 5` (true).              |
| \|\|      | Or.  Example: `3 > 5 || 3 < 2` (false).              |
| !         | Not.  Example: `1 !== 2` (true).                     |

## Switch Statements

You can also use `switch` statements to avoid some long `if` statements.  I don't often use these, so I wouldn't recommend it unless you have a good reason.

```js
let dayOfWeek = "Wednesday";

switch(dayOfWeek) {
    case "Monday":
        console.log("Ugh, another Monday");
        break;
    case "Tuesday": 
        console.log("Taco Tuesday!");
        break;
    case "Wednesday":
        console.log("Guess what day it is?");
        break;
    default:
        console.log("Weekend!  Or close enough!");
        break;
}
```

Notice that we have to use a `break;` statement at the end of each `case`.  This prevents all subsequent cases from being executed once the correct one is found.  `default` is like `else` - a catch-all for any condition not met.

## Wrap Up and Exercise

Here we covered how to use `if` statements with optional `else if` and `else` clauses.  We covered comparison operators to create and combine conditions.  The `switch` statement was explained, but it is not commonly used.

If you'd like to practice using `if` statements, try implementing these scenarios.

1. Set two numbers as variables and compare them.  Ouput the result of the comparison.
2. Write a program to comment on someone's preferred programming language.
