---
title: Step 2
order: 2
---

# An Intro to Ember

## What is Ember?

Ember or more specifically EmberJS (JS stands for **J** ava **S** cript) is a framework that helps you build entire websites using JavaScript. Many modern websites are built based on JavaScript frameworks like EmberJS alone. JavaScript websites or so-called **web applications** tend to not only feel faster to their users, but also provide much more interactivity.

An example of a classic website is a news website such as [The Daily Mail](https://www.dailymail.co.uk) or [Tagesschau](https://www.tagesschau.de). These provide content for you to read but leave almost no room for interaction. Their main goal is presentation of information.

An example for a modern web application is a service like [Gmail](https://gmail.com) or [Dropbox Paper](https://paper.dropbox.com).
Features like your message editor or the message search integrate into the website smoothly and allow user interaction.

When building web applications the Ember framework supports you by integrating into JavaScript code seamlessly
(and which you'll be using to build your app) and the entire framework itself is written in JavaScript, too.
Ember helps you to manage JavaScript files, allows you to edit them and run them in the browser. To achieve this, Ember will generate new JavaScript files for you on command, that you can modify further in your text editor to build your app.

The app we'll be building today will in the end look something like this:

![Super Rentals App](/images/super_rentals_demo.png)

In this section we'll learn some of the basic principles of Ember and how we can use an important tool - the Ember CLI (CLI stands for **C**ommand **L**ine **I** nterface) - to make building our application really easy.

## Generate a new app project

In the following section you will learn about the [Ember CLI](https://cli.emberjs.com/release/). You will learn how to use it to
- create a new app project to get started with your application
- serve an EmberJS application from your own computer and see it running in your browser

### Exercise 2a: Generate an application

- Prerequisites: This step requires the Ember CLI to already be installed on your computer. You can check if it's installed by typing into your terminal: `ember -v`. If you see `ember: Command not found`, it means that Ember CLI is not installed on your computer. Please review the [installation instructions from the pre-installation step](#TODO: INSERT LINK TO PREINSTALL PARTY GUIDELINES)
- Open your terminal
- Type in `cd ~/Desktop/emberginners-workshop` and hit enter to go into the correct folder to create your app in
- Type in `ember new super-rentals` and hit enter and investigate the console output. Wait until no new messages show up in your terminal

![Example Generate App](/images/ember_demo-2a.gif)

Here you can see all the files that make up the app. The Ember CLI created a new folder for us, called  `app` which alredy contains actual app code and where we will add our own code to create our first web application. You can ignore all the other folders like `config/`, `node_modules/` or `vendor/` today. In the end Ember will build the app that runs in the browser out of all these files that you can see here.
