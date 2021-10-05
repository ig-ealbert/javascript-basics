# Loops

## Overview

In order to run the same code multiple times, copying and pasting it seems like the obvious option.  In addition to being unwieldy, that's also a nightmare if you need to make any sort of update or fix!  Luckily, there are loops to repeat code.

## For Loop

`for` loops allow us to execute the same code multiple times.

### Basic For Loop

The most basic form is one where you know exactly how many times you want to do something.

```js
for(let i = 0; i < 10; i++) {
    console.log(`Executing code run #${i}`);
}
```

This will print the message 10 times, each time with a different value for the run number.

### Iterating Over an Array

You can run some code for each item in an array.

```js
const animals = ["cat", "dog", "panda", "bird", "fish"];

for (let animal of animals) {
    console.log(`A ${animal} would make a great pet!`);
}
```

Here we loop through the list of animals by letting JavaScript handle the hard work.  It will start at the beginning of the `animals` array and assign the first animal to the variable `animal`.  When it's done, it will move onto the next animal.  We don't explicitly have to tell it to do so.

### Iterating Over an Object

You can also run some code for each key in an object.  You can access the value from the key.

```js
const letterToNumber = {
    "a": 1,
    "b": 2,
    "c": 3
}

for(let letter in letterToNumber) {
    console.log(`The letter ${letter} corresponds to the number ${letterToNumber[letter]}`);
}
```

That will print out something like `The letter a corresponds to the number 1` for each key in the object.

## While Loop

You might want to run code until a condition is met.  This is the use case for `while`.

```js
let times = 1;

while(times <= 10) {
    console.log(`Done the while loop ${times} times.`);
    times++; // same as times = times + 1
}
```

The danger of while loops is that they have to end!  What would happen if we left out the `times++;` statement?  Infinite loops are NOT FUN!  Be careful!

## Indexing

As briefly mentioned in the variables lesson, indexing in JavaScript counts from 0.  Be careful when using indices in a loop.  For example:

```js
const greeting = "Hello";

for(let i = 1; i < greeting.length; i++) {
    console.log(greeting[i]);
}
```

This will print out

```
e
l
l
o
```

Why?  Because the `H` is index 0!

What do you think would happen if instead of `greeting.length` we used `6`?  Don't go outside of index bounds!

```
H E L L O
0 1 2 3 4
```

## Wrap Up and Exercise

Here we covered how to use `for` loops in 3 ways.  The first is the most basic where you state how many times to run code.  The second is looping through an array to do something for each element in it.  The third is looping through an object to do something for each key.

We also covered while loops, which can be used to run code until a condition is met.  They are a bit dangerous though, so be careful with your condition!  Make sure it becomes true at some point!

If you'd like to practice using loops, try implementing these scenarios.

1. Countdown for the new year, starting from 10!  Print out "Happy New Year!" at the end.
2. Print out the numbers in order, starting from 1, until you find one that is both divisible by 3 and divisible by 5.  Hint: `%` will give you the remainder of a division operation.  For example, `5 % 3 = 2`.
