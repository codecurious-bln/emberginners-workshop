---
title: Step 2 - Git Clone
order: 2
---

## Exercise 2a: Cloning a git repo

To clone a git repo you can run the following:

```bash
git clone https://github.com/simplabs/emberginners-workshop-app.git
```

this will create a folder called `emberginners-workshop-app` that you can `cd` into.

Something to note when you're cloning a repo that uses npm, you need to install the repos depenedencies before you can do anything

```bash
cd emberginners-workshop-app

npm install
```

## Exercise 2b: Run JavaScript from a file

- Open your text editor
- Open the new folder that was created when we used `git clone`
- start the server using `npm start`
- visit [http://localhost:4200/demos/demo-2b.html](http://localhost:4200/demos/demo-2b.html)
  - you should see "hello there" but nothing should happen
- Open the file `/public/demo/demo-2b.html` in your text editor
- Investigate the `<script type="text/javascript"></script>` section in your editor
- Fill in a snippet of JavaScript code from the previous exercise (1a) into the snippet below the `// comment`
- Reload the page in the browser. What do you see?
- Trouble with the exercise? Open `/public/demo/demo-2b-solution.html` in your editor and browser

## Exercise 2c: Read and write to variables

- Open the file `/public/demo/demo-2c.html` in your text editor
- visit [http://localhost:4200/demos/demo-2c.html](http://localhost:4200/demos/demo-2c.html)
- Investigate the current `alert()` statement in your editor. What do you see?
- Open your browser console (as described in Exercise 1a). What does the error message tell you about what is happening on the website? Try clicking the link that is provided with the error message. What do you see?
- Find out how to make your page alert the phrase `I learn all day` without changing the line with the `alert` statement
- Make your program alert `I learn all day` first and then alert `I code all day` second by using only one variable in your program
