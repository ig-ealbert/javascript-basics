# Variables

## Overview

Variables are how we work with data in JavaScript.  Here we'll cover the basic types of variables and how to use them.  We're focusing on the basics, so this is not an exhaustive list.

## Introduction

Let's first go over some common things you'll see in code snippets.

### Comments

To describe pieces of code, we'll use comments.  These descriptions have no impact on the functionality of the program, but are used for human readability.

There are two types of comments.

```js
// Double-slash is a one-line comment
// Each comment line, in this format, starts with //

/*
Slash-star indicates multi-line comments.
Here you can have multiple lines inside of a comment block
without having to start each line with //.
*/
```

### `console.log`

To print out the result of some code, we will be using `console.log`.

There are two patterns we will use.

```js
console.log("Hello World!");
// prints out Hello World!

const name = "Leeroy Jenkins";
console.log(`Hello ${name}!`);
// prints out Hello Leeroy Jenkins!
```

That second one looks a bit confusing, but it allows us to intersperse code and text more easily than concatenating strings.  Note the backticks here are what let us do that.

### Semicolons

Using semicolons to indicate the end of a statement is recommended, so they will be used here.

### `const` and `let`

We can declare variables in two ways.  One means the data will never change and cannot change.  The other means that the variable is truly variable - it can be changed.

```js
// This cannot change
const name = "Leeroy Jenkins";
// This can be changed
let cost = 4;

// This will throw an error because it is a const!
name = "Murgur Murgurgle";
// This will work because it is a let!
cost = 5;
```

We only have to state this declaration once.  As you can see, we only say `const` or `let` the first time we create a variable.  When we change it, we don't have to do this.

Now let's start to look at some types of variables.

## Strings

The typical computer science introduction to any language is "Hello World".  Let's use that as an example.

```js
const greeting = "Hello World!";
console.log(greeting);
// prints out Hello World!
```

Strings can be indexed so you can update individual characters or split them up.

```js
let greeting = "Hello World!";
const miniGreeting = greeting.substring(0, 5);
console.log(miniGreeting);
// prints out Hello

greeting[11] = "?";
console.log(greeting);
// prints out Hello World?

console.log(greeting.indexOf("e"));
// prints out 1
// more on indexing in the Arrays section
```

## Numbers

Numbers are just that - numbers!  You can use them for math.

```js
const num1 = 3;
const num2 = 2;
console.log(num1 + num2);
// prints out 5

console.log(`${num1} * ${num2} = ${num1 * num2});
// prints out 3 * 2  = 6
```

## Booleans

Booleans mean a true or false value.  You can use these to do logic.

```js
const isOP = true;

if (isOP) {
    nerf();
}
```

You can run comparisons on values to get booleans.

```js
let cost = 4;

// cost < 5 results in true - a boolean!
if (cost < 5) {
    nerf();
}

let isOriginalCost = cost === 4; // === checks for equality
let isNefedCost = !isOriginalCost; // ! means "not"
```

## Arrays

Arrays hold multiple values in an order.  They are referred to as "lists" in some other languages.

```js
let animals = ["dog", "cat", "bird", "panda", "fish"];

console.log(animals.length);
// prints out 5

for(let animal of animals) {
    console.log(`A ${animal} would make a great pet!`);
}
```

You can add and remove elements from the end of an array.

```js
let animals = ["dog", "cat", "bird", "panda", "fish"];
animals.push("murloc");
console.log(animals.length);
// prints out 6

console.log(animals.pop());
// prints out murloc and removes it from the array
console.log(animals.length());
// prints out 5
```

Indexing counts items starting at 0.  In other words, the first item in an array is at index 0.

```js
let animals = ["dog", "cat", "bird", "panda", "fish"];
console.log(animals[0]);
// prints out dog
```

Here's a visual example with a string.

```
H E L L O
0 1 2 3 4
```

Be careful not to access index 5, as there is no letter corresponding to index 5!

## Objects

Objects often store more complex information such as key and value pairs.

```js
const letterToNumber = {
    "a": 1,
    "b": 2,
    "c": 3
}

console.log(letterToNumber["a"]);
console.log(letterToNumber.a);
// both of these print out 1

// Add an entry to an object
letterToNumber["d"] = 4;

// Update an entry in an object
letterToNumber["e"] = 6; // Whoops!
letterToNumber["e"] = 5; // Much better!

for (let letter in letterToNumber) {
    console.log(`The letter ${letter} corresponds to the number ${letterToNumber[letter]}.`);
}
```

## Wrap Up and Exercise

Those are the basics of variables!

Some of the explanations used concepts we will cover in more detail in later lessons.  Don't worry if something wasn't clear!

If you'd like to practice using variables, try these exercises.

  1. Write a program that defines your name and age.  Then print out a message that states your name and how old you are.
  2. Write a list of your favorite foods and print them out in order.
  3. Create an object containing 3 nouns and the adjectives you associate with them.  Then print out a description of each noun.  For example, "A bunny is cute", where "bunny" is the noun and "cute" is the adjective.
