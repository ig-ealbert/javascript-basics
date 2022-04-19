# Server-Side JavaScript

## Overview

JavaScript can also be used for programs outside of the browser.  `node.js` is the library that lets you do this.  It allows you to interact with files and databases, which was a security limitation in purely client-side JavaScript.  You can, of course, also run all of the basics that we covered in the first 4 lessons.

## Modules

Server-side JavaScript allows you to organize and share your code between files.  This is done by using modules, which is a fancy name for code split into different files.  You can then import and export your functions and variables for use in other files.

There are two ways to do this.

### Import and Export

You can use a library like [`CommonJS`](https://en.wikipedia.org/wiki/CommonJS) which allows for using `import` and `export`.

You can also change the file extension of your `.js` files to `.mjs` to explicitly make them modules.  This will also allow you to use `import` and `export`.

```js
// file1.js

export function shareMe() {
    console.log("I am being shared!");
}

// file2.js
import { shareMe } from "./file1";

shareMe();
```

Just make sure that your imported functions and variables don't conflict with anything you have already in the file!  If that is unavoidable, you can alias them.

```js
import { shareMe as myShareMe } from "./file1";

// locally defined function, different from imported one
function shareMe() {
    console.log("Haha, no sharing of this one!  Use myShareMe for that!");
}

shareMe();
myShareMe();
```

### Require

You can also use `require`, which is built into node.js.  When using this method, you must have a `module.exports` line in your file to explain what gets exported.

```js
// file1.js

function shareMe() {
    console.log("I am being shared!");
}

module.exports = shareMe;

// file2.js
shareMe = require("./file1");

shareMe();
```

## Libraries

Modules also allow you to import functionality from other people, such as [published npm libraries](https://www.npmjs.com/).  This would be done via `npm install`, which is out of the scope of this lesson.  You can also import libraries that are installed with node.js, but not automatically included in your projects.

```js
import assert from 'assert';

assert.strictEqual(1, 1);
```

## Asynchronous JavaScript

You also get access to files and databases, as well as other typically long-running interactions.  Computers think very fast, so anything that takes more than nanoseconds is likely asynchronous.  Thankfully, this is pretty easy with `async`/`await`.  The code snippet will just be pseudocode, but hopefully it gives you an idea of what can be done.

```js
async function printFileContents() {
    const fileName = "myFile.txt";
    const fileContent = await readFile(fileName);
    console.log(fileContent);
}
```

`await` tells JavaScript to stop executing the rest of the script until the awaited line completes.  It sounds weird, but normally JavaScript will keep on going, regardless of whether it has read the file already or not.  Not gonna wait around unless you tell it to!

Any function that uses `await` must be `async` to show it's an asynchronous function.  The result of calling this function must also be `await`ed.

## TypeScript

In the [variables](01-variables.md) lesson, we went over some basic types.  These are not explicitly stated in JavaScript, and it's pretty lenient on what it lets you do.  This can lead to some unexpected runtime errors or incorrect results.  If you want to add types explicitly to your code, TypeScript is for you.  This helps check for errors before you run your program.  The only downside is that it has to be compiled into JavaScript in order to run.

```ts
const myString: string = "Hello World!";

function incrementNumber(value: number): number {
    return value + 1;
}
```

The first example shows how to add a type to a variable.

The second example shows how to add types to parameters and return values of functions.

The benefit here would be that if we tried to do something like `incrementNumber(myString)`, it would tell us in an IDE like Visual Studio Code, as well as at compile time, that we're not gonna be happy with the result.  In pure JavaScript, it would allow this, and we'd get the result `Hello World!1`.  This is **probably** not what we're trying to do, so best to be aware.

## Summary

Server-side JavaScript lets you do things you can't do in the browser.  It allows for interaction with the file system and databases, asynchronous calls, modules, and typing.

For beginners, stick with client-side JavaScript until you're comfortable, and then explore creating a basic node.js project to try out the new tools you get with it.

## Links to Further Reading

* [npm](https://www.npmjs.com/)
* [MDN Async/Await](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function)
* [MDN Modules](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules)
* [TypeScript](https://www.typescriptlang.org/)
