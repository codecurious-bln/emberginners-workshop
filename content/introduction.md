---
title: Pre-Install Party
---

This is a workshop to teach those who have never programmed before (or at least never programmed with JavaScript - the programming language of the web) a few basics in web and JavaScript development. This also includes a short introduction into the JavaScript framework EmberJS which we will use to build our very first web application.

## How to follow the workshop

This workshop and its materials are based on the workshop slides that you can find online at [#url-here](#url-here).
You can follow the slides and go back to previous lessons at any time, either during or after the workshop.

Do you have feedback or improvements for the workshop materials? Talk to us during the workshop and we'd be looking forward to incorporate your suggestion into the next edition of this project.

## What does web development mean?

Learning more about web development allows you to build your own websites and web apps that you can publish online and share with the world! If you ever had the idea for a new project or a tool that can be used online, then this workshop is just for you.

As someone who builds websites and web apps, you're using different technologies or so-called **programming languages**. The main languages used on the web are **HTML**, **CSS** and **JavaScript**. In the scope of this course we will focus on JavaScript, but if you have interest in learning more about HTML and CSS, we'd like to encourage you to follow your interest. We can also share more materials on these technologies for further learning at the end of the workshop.

With JavaScript as one of the main languages of the web, we can - once we know how to read and write JavaScript code - build our own, interactive web experiences. Many websites nowadays heavily depend on JavaScript to run. These websites which are mainly based on JavaScript programs are also called **single-page applications**. Examples for popular single-page applications online are [gmail.com](https://gmail.com), [Twitter](https://twitter.com), [Linkedin](https://linkedin.com) or [Instagram](https://instagram.com). Building single-page applications allows us to build modern websites, which feel faster and are more responsive than the traditional websites we are used to from the 90s.

## What is Ember?

Ember is a specific **JavaScript framework** that allows us to build fast single-page applications. As a framework it provides us with a way to write JavaScript code to create our app, but it also provides us with many useful tools to do so. We will learn more about what these tools are about at the workshop.

![Tomster & Zoey Mascots](/images/mascots.png)

If you're curious about what you can build with Ember, check out a few of the following websites that are built using it:


- Showcase 1: [Linkedin.com](https://www.linkedin.com/)
![Linkedin EmberJS Showcase](/images/linkedin.png)

- Showcase 2: [Trainline](https://trainline.fr)
![Trainline EmberJS Showcase](/images/trainline.png)

- Showcase 3: [Playstation Store](https://store.playstation.com/de-de/home/games)
![Playstation EmberJS Showcase](/images/ps.png)


## How does this workshop work?

This workshop is about learning something new that helps you to explore new interests and provide basic knowledge to continue learning.
What's important in that regard?

- Keep an open mind
- Be patient
- Help each other out
- Ask the mentors questions!
- Celebrate your successes today

Feel free to pair with one or two other people in the group. If you prefer working on your own, this is also great - see whatever works best for you!

## Getting setup

To be able to follow the workshop, we need to install several programs onto our computer and get familiar with a few.

### Installation (Part 1)


#### Installing a text editor

To be able to write our first web application we need to install a text editor that allows us to edit our program. In the scope for this workshop we will use **Atom** which is a free text editor that's well suited for development, too. You can download and install it over [here](https://atom.io/).

#### Installing a browser

Several browsers provide us with tools that help us to develop our web application. In the scope of this workshop we'd like to use **Google Chrome**. If you haven't got it on your computer yet, you can download and install it over [here](https://www.google.com/chrome/).


### Getting familiar with the terminal

A terminal is a program that allows you to run, stop and interact with programs on your computer using text-based commands. Other terms that are used to describe a terminal, are "console", "shell" or "command line".

#### Opening your terminal

You can open your terminal as follows:

* Mac: Hit Command + Space key and type "Terminal" and open it hitting enter
* Linux (e.g. Ubuntu): Hit Control + Alt + T
* Windows: Install and open the [Windows Subsystem for Linux for Windows 10](https://superuser.com/questions/608106/how-can-i-use-a-bash-like-shell-on-windows) or the [Cygwin tool set](https://www.cygwin.com/)

#### Starting + Stopping Processes

Each terminal window or terminal tab will open with a new line mentioning your username on your computer, your computer's name followed by an empty line:

![Termimal Window](/images/terminal.png)


Any program that you run via the terminal can be stopped and re-run. To start a program or process you need to type in the respective command and hit enter, to stop a command use Ctrl + C.

Throughout this workshop we will mention several commands that you need to run in the terminal.

##### Exercise: Start and Stop a Process

There is a program you can run to "knock on the door" of a website and check if it's currently online. The program is called **ping**. This program has a simple terminal command that you can use to run it, also called `ping` and it can be run in your terminal window by typing the following:

```bash
ping replace-this-with-the-url-of-a-website
```

If we for example wanted to check the current status of the EmberJS website, we could run:

```bash
ping emberjs.com
```
Now, try it yourself:
- "ping" a website of your choice via your terminal using the `ping` command
- What do you see in the terminal window?
- Stop the process by using the control mentioned earlier in this section

The `ping` command takes in a url which can be different anytime the program is run and is free to user choice. A text or number that is used in combination with a command is called a **parameter**. During the workshop we will learn about more commands that take in parameters for running their respective program.

##### Exercise: Navigate across directories

Your terminal allows you to navigate through the folders of your computer and create new directories, too. This can be really handy when managing the code files you'll be creating, editing and saving in this workshop.

If you want to create a new folder, you can run `mkdir`, the command for **m** a **k** ing **dir** ectories, followed by the name you'd like to have for that particular folder as a parameter:


```
mkdir my-new-folder
```

This will create an empty folder right where you are in your directory structure. To see what's inside the folder, you can navigate into it and list its content. To do so, you can run the command for navigation as follows:

```
cd my-new-folder
```

And to list the content of the folder, you can run:

```
ls
```

Go ahead and try it:

- Create a new folder called `ember-workshop` with terminal commands
- Navigate into your newly created folder using the terminal
- List the folder's content. What do you see in your shell window?


Did you also know that you can copy-paste any of the commands from this tutorial into your terminal window? Hit Control + C (Windows + Linux) or Cmd + C (Mac) while highlighting the command to copy it and use Control + V (or Cmd + V on Mac) while focussing your terminal window to paste it. This is especially useful for long commands that might take a while to type out.


### Installation (Part 2)

In this part of the installation process, we'll install several tools that are needed for developing our JavaScript application tomorrow. To follow the workshop you will need to install

- Git - a tool for downloading code examples for this workshop
- Node - a JavaScript runtime that comes together with `npm` which helps us to install useful libraries for the application we're building
- Ember CLI - the command line tool we'll be using to run and manage our Ember app

You can install all you need using the [Getting Started Guide for Your Ember Installation](https://guides.emberjs.com/release/getting-started/).

Feeling stuck and don't know how to continue your installation? Feel free to ask a mentor and/or take a look at what your neighbours are doing!
