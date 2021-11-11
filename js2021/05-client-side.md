# Client-Side JavaScript

## Overview

Now that you've seen an introduction to the basics of JavaScript, you might be wondering why it is the language of the web.  JavaScript is built into browsers, and can interact with the DOM (Document Object Model).  In other words, you can add functionality to your websites with JavaScript!

Client-side means "in-browser".  This comes with security limitations like not being able to access a file system or a database, but we'll focus on the benefits of being able to update what displays on a website.

## Structure

For a basic client-side-only website, you'll have 3 files:
 * HTML
 * CSS
 * JavaScript

 The HTML file contains the elements that will exist on the website.  It defines the UI.

 The CSS file contains the styling information for the elements.

 The JavaScript file contains logic to add functionality to the page.

 THe HTML file imports both the CSS and JavaScript files so they take effect.

## Basic Example

The walkthroughs I created in 2017 rely on this client-side specific functionality.  Let's take a look at the [arrays example](../js2017/arrays/arrays.md).

First we have the HTML file, which contains the elements for the UI, and imports the CSS and JavaScript files.

```html
<!DOCTYPE html>
<html>
<head>
<title>Arrays</title>
<link rel="stylesheet" type="text/css" href="arrays.css" />
</head>
<body>
    <table>
        <tr>
            <td><button onClick="goLeft()">&lt;</button></td>
            <td><div class="fixed"><img id="catPic" src="images/Cat1.jpg" /></div></td>
            <td><button onClick="goRight()">&gt;</button></td>
        </tr>
    </table>
    <script type="text/javascript" src="arrays.js"></script>
</body>
</html>
```

The line with `link` and the line with `script` show how to import the other files so they are applied to the HTML page.

JavaScript can modify these elements.  In the arrays example, we modify the `src` attribute of the `img` (image) to change which picture is displayed.  You can do more than that, like changing text, adding elements, removing elements, styling them, and more!

```js
let catPic = document.getElementById("catPic");
```

JavaScript gives you tools to select elements from the webpage and interact with them.  The previous code snippet gets the image element and saves it as `catPic`.  The following code snippet would change the image displayed in that element.

```js
catPic.src = "images/Cat2.jpg";
```

## Events

You can also handle events in JavaScript.  In the arrays example, we create button click event handlers to change the image displayed.  The `onclick` attribute of the `button` element lets us specify a function, which we define in the JavaScript file.

```html
<button onClick="goLeft()">&lt;</button>
```

```js
function goLeft() {
    catPic.src = "images/Cat2.jpg";
}
```

This is a simplified example - check out the [full example](../js2017/arrays/arrays.md).

## Inspector and Console

From the browser, you can inspect and play with the elements and styling of any webpage (locally only, of course).  These will help any aspiring web developer to experiment!

In Chrome (or any modern web browser), right-click a page and choose "Inspect".  This should bring up a "dev tools" window, where you can view the DOM (the HTML elements), the styles, and try out some JavaScript in the console.  This is also a great way to debug, if you're working on a client-side website and something isn't quite right.

## Other Examples

Feel free to try out the other examples from the `js2017` folder in this repo.  The markdown file walks you through how to fill in the `.js` file with the correct code.  This requires you to have the files locally, so a `git clone` is suggested first.

## Summary

Without an HTML file, these kinds of interactions don't mean anything, so that's why these are specific to the client-side, in-browser JavaScript.  There's a lot more that you can do, and MDN will be your friend there for reference material.  Some links are included below.

## Links to Further Reading

* [MDN CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
* [MDN Manipulating DOM](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Manipulating_documents)
* [MDN Append Element](https://developer.mozilla.org/en-US/docs/Web/API/Element/append)
* [MDN Create Element](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElement)