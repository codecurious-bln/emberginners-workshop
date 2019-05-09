---
title: Step 1
order: 1
---

# An Intro to JavaScript

## What is JavaScript used for?

JavaScript is a programming language that empowers its users to build things on the web! What does building things on the web this specifically mean? To understand this better, let's take a look what a browser, a program like Chrome or Firefox, actually does:

## What do Browsers Do?

A web browser (commonly referred to as a browser) is a software application for accessing information on the World Wide Web. Each individual web page, image, and video is identified by a url (e.g. `http://www.simplabs.com`) enabling browsers to retrieve these resources from a web server and display them on the user's device - which is your computer or your smartphone.

Your browser is an application that can parse - which means, read and interpret - information via different types of data formats stored in files. As a reference, your Microsoft Office or OpenOffice editor is an application that can parse information that is stored in the form of `.doc` or `odt` files. In a similar fashion, certain types of files can be parsed by browsers which are mostly `.html` (HTML), `.css` (CSS) and `.js` (JavaScript) files.

In the scope of this workshop we won't be able to take a deeper look into the former two, HTML and CSS, themselves. If you want to learn more about them after the workshop, feel encouraged to learn more about them through web courses or user groups in your area.

Instead we will focus on JavaScript and how we can use and create `.js` files, that can be run in the browser so that it will display our first web application that we're going to build today!

## What is JavaScript?

JavaScript is a dynamic programming language that runs in the browser. This means that your browser (e.g. Chrome, Firefox, Internet Explorer) can not only read JavaScript files,
but is also able to carry them out. A JavaScript file is any text file with a `.js` filename ending and text content which follows the JavaScript language syntax.

In the following section you will learn more about how you can make JavaScript code run in your own browser.

### Running JavaScript directly in your browser

In the following section we will see how we can run JavaScript code directly in our browser. We will not require any text editor as such and we won't need to create any JavaScript files beforehand.
Instead, we will use a **tool** that is pre-installed for us in any browser to write JavaScript and run it subsequently.

#### Exercise 1a: Showing a message box

- Open your browser (Chrome and Firefox are the best options for following this workshop. You can download them here: [Chrome](https://www.google.com/chrome/) [Firefox](https://www.mozilla.org/firefox/))
- Do one of the following:
    - Any operating system: right click into the window, select "Inspect" and click on the "Console" tab
    - On Mac: Hit Option + Command + I
    - On Windows: F12 or Control + Shift + I
    - On Linux (e.g. Ubuntu, Fedora): F12 or Control + Shift + I
- Type into the window right next to the small arrow: `alert("Hello World!")` and hit Enter.

![Console Demo 1.a](/images/console_demo-1a.png)

- Type into the window right next to the small arrow `console.log("Hello World!")` and hit Enter. What happens now?

#### Exercise 1b: Run JavaScript from a file

- Open your text editor
- Open the file `/demo-1b.html` in your text editor (TODO: lol, no one knows how file directories work, right)
- Open the file in your browser (e.g. double-click on it in your file directory or in your editor menu)
- Investigate the `<script type="text/javascript"></script>` section
- Fill in a snippet of JavaScript code from the previous exercise into the snippet below the `// comment`
- Reload the page in the browser. What do you see?
- Trouble with the exercise? Open `/demo-1b-solution.html` in your editor and browser

## What are variables?

Variables in JavaScript provide a way to **store** and to **retrieve** words, numbers and other more complex things in your program.
A variable acts as a container for these so-called _values_. You can _declare_ a variable and fill it in with a value by using a dedicated keyword and the _assign_ operator `=`.

In the scope of this workshop we will learn about one particular variable keyword called `let`. If you continue to learn more about JavaScript after this workshop, you might encounter other variable keywords as well, but for now, we can do everything we want to achieve in this course by focussing on `let` only.

If you, for example, wanted to create a variable that stores your favorite color, can write the following:

```js
let color = 'purple';
```

This line does 3 things:

- It creates a new variable, a container for any word or number you want to store
- It fills in the variable `color` with the word `purple`
- It allows you to retrieve the word `purple` any time again in your code by reading from the variable `color`

You can choose almost any word that comes to your mind, when naming a variable. It's also possible to include numbers in your variable name.

After a variable has been declared, you can read its value by using its name further down your program:


```js
let color = 'purple';

// ...other code

console.log(color);
// => prints "purple" to your console
```

Also, after a variable has been declared for the first time, you can update its value anytime further down in your code as follows:

```js
let color = 'purple';

// ...other code

color = 'blue';
```

When **updating** an **already declared** variable, you **must not** use the variable keyword. The variable keyword is only used when you declare a new variable for the first time.

Besides that, we also see that each code instruction - a so-called _statement_ - ends with a semi-colon `;`. It acts as like a colon after a phrase indicating to the browser that a full code instruction ends right there.

Note: In the examples above we're assigning a word, or a so-called _string_, to our variable `color`. A string describes a number of characters, either letters, numbers or special characters, which are _stringed_ together. A string always needs to be written in quotation marks - you are free to choose either single quotes `'` or double quotes `"`.


#### Exercise 1c: Read and write to variables

- Open your text editor
- Open the file `/demo-1c.html` in your text editor
- Open the file in your browser as done in the previous exercise
- Investigate the current `alert()` statement. What do you see?
- Open your browser console (as described in Exercise 1a). What does the error message tell you about what is happening on the website? Try clicking the link that is provided with the error message. What do you see?
- Find out how to make your page alert the phrase `I learn all day` without changing the line with the `alert` statement
- Make your program alert `I learn all day` first and then alert `I code all day` second by using only one variable in your program
