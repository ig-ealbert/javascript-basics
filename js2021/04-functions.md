# Functions

## Overview

In the previous lesson, we covered loops as a way to repeat code.  Functions provide the same reusability of code, but with added benefits.  You can effectively compress multiple lines of code that achieve a goal into a single line of code elsewhere.  Given proper naming conventions, it can become very easy to understand what the code does.  For example, `printShoppingList()` should do what the name says.  Additionally, functions allow for customization each time the function is run.  This way, the same code can do slightly different things each time.

## Basic Function

Here we have an [annoyotron](https://static.wikia.nocookie.net/hearthstone_gamepedia/images/e/ec/Annoy-o-Tron%2812181%29.png/revision/latest?cb=20210525071252), who will greet the world.

```js
// declaration
function annoyotron() {
    for (let i = 0; i < 3; i++) {
        console.log("Hello!");
    }
}

// invocation
annoyotron();
```

We wrapped a for loop inside a function with name `annoyotron`.  The parentheses after the name are a good indication that what we have is a function, in addition to the keyword `function` before it.  To call the function and actually have it do something, we just write the name of the function followed by parentheses.

Recalling loops from our last lesson, the output will be:

```
Hello!
Hello!
Hello!
```

## Parameters

To customize a function, we can add parameters.  Let's start off easy and change the greeting.

```js
// declaration
function annoyotron(greeting) {
    for (let i = 0; i < 3; i++) {
        console.log(greeting);
    }
}

// invocation
annoyotron("Howdy!");
annoyotron("Hi!");
```

Here we expect a greeting passed into the function invocation (call), which determines what will be printed when the for loop runs.  We call it `greeting` as a variable name, and then use the same name in place of the hardcoded `"Hello!"` we had before.

We can also have multiple parameters.

```js
// declaration
function annoyotron(greeting, times) {
    for (let i = 0; i < times; i++) {
        console.log(greeting);
    }
}

// invocation
annoyotron("Howdy!", 3);
annoyotron("Hi!", 5);
```

Here we additionally specify the number of times to be greeted.

## Optional Parameters and Default Values

If you'd like to fall back to a given value if the parameter is not specified, that is possible.

```js
// declaration
function annoyotron(greeting = "Hello", times = 3) {
    for (let i = 0; i < times; i++) {
        console.log(greeting);
    }
}

// invocation
annoyotron("Howdy!", 3);
annoyotron("Howdy!"); // This gets the default value of 3 times
annoyotron("Hi!", 5);
annoyotron(); // This uses both default values
```

Here, if a greeting isn't specified, it becomes `"Hello"`.  If the number of times is not specified, it becomes `3`.  However, note that we cannot only specify the number of times, like in `annoyotron(4)`, because it always expects the first parameter to be the greeting.  In that case, supply both parameters even if the first one is the same as the default.

## Why Functions?

It's good to group your code into pieces that can be combined later.  This makes it easy to debug if something goes wrong (you know where the code for that specific piece is), and it also makes it easy to read and understand.  For example, you don't need to know how this works, but you know what it does.

```js
addItemToCart("bread");
addItemToCart("nutella");
checkout();
```

## Wrap Up and Exercise

Here we covered how to write a function and why it might be useful.  We covered basic functions, functions with parameters, and functions with default values.

If you'd like to practice using functions, try implementing these scenarios.

1. Write a function that takes one parameter and prints out all the numbers from 1 to that number.
2. Write a function that takes two numbers as parameters and multiplies those numbers together.
3. Write a function that takes two strings as parameters and concatenates those strings (append the second string to the first one).  If you'd like to try out default values, make the second parameter default to `"!"`.
