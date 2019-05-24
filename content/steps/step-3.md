---
title: Step 3
order: 3
---

# An Intro to Routing in Ember

## What is routing?

Our application allows us to navigate to different pages or so-called _routes_ of it via url. The url is the name of a sub page in our website, which we can type into the browser navigation bar to allow us to land on that part of our app. The url allows to access different `routes` of our Ember app.

Routing in web applications is important, since it enables users to share a specific part of the app with others. E.g. if you want a friend to take a look at your super-rentals overview page, you can just send them the link (a.k.a url) that opens that part of the application.

To create routes that can be accessed via certain urls, we use the Ember CLI and more specifically its **generator** s. Using the `ember generate` command we can create all kinds of things in our application, including routes.


### Exercise 3a: Generate a new route in your Ember app

- Open your terminal
- Type in `ember generate route about` and hit enter. Ember CLI will create several JavaScript files for you and edit some of them automatically for you. Check out the changes in these files in your text editor!
- Open `app/router.js` and investigate the newly added route: `this.route('about')`
- Open your application in your browser to see the new route in action: `http://localhost:4200/about`
- In our app, a route is represented by a JavaScript file (`.js` file ending) and a template (`.hbs` file ending). Open the template `app/templates/about.hbs` in your text editor
- Copy-paste the following into your template (`app/templates/about.hbs`)

```html
<div class="jumbo">
  <div class="right tomster"></div>
  <h2>About Super Rentals</h2>
  <p>
    The Super Rentals website is a delightful project created to explore Ember.
    By building a property rental site, we can simultaneously imagine traveling
    AND building Ember applications.
  </p>
</div>
```

- Save the file `app/templates/about.hbs` and go back to your app in the browser. You can find the new page at [http://localhost:4200/about](http://localhost:4200/about). What changed?

## What are links?

In websites and web applications links allow the user to navigate to another sub page of the website with one single click. In an Ember app the handy `{{link-to}}` helper allows us to link to separate pages. When a user clicks an element that is wrapped inside of a `{{link-to}}`, they will be redirected to the route the link is pointing to.

Imagine we had an overview page somewhere in our application with the following markup:

```hbs
<h1>Overview</h1>
Go to Contact Page
```

If we e.g. wanted to link the wording `Go to Contact Page` to a route, called `contact`, we could e.g. create a link to that page as follows:

```hbs
<h1>Overview</h1>
{{#link-to "contact"}}Go to Contact Page{{/link-to}}
```


If the user now clicks on the sentence `Go to Contact Page` in our app, they will be redirected to the Contact route.

The `{{link-to}}` helper will point to the correct route according to the route name. The route name is given to the page through its file name. This means you will find the definition for the `contact` route in the files `app/routes/contact.js` and `app/templates/contact.hbs`. Many things in an Ember app are defined and named by their respective file names. Ember as a framework emphasises naming conventions and makes it possible for us to recognise how a page is called by only checking its file name.


### Exercise 3b: Link a page to another page

In this exercise we'd like to 1. create a new page called `rentals` and 2. link that new page to another, already existing page in our app

- Generate a new route called `rentals` in a similar way as you did in the previous exercise
- Replace the content of the file `app/templates/rentals.hbs` with the following:

```html
<div class="jumbo">
  <div class="right tomster"></div>
  <h2>Welcome!</h2>
  <p>We hope you find exactly what you're looking for in a place to stay.</p>
  <!-- Replace me with a link -->
</div>
```

- Visit the rentals page in your browser. Which url do you have to use? What do you see now?
- Create a link to the `about` route right where the replacement placeholder is in the template. The link should read `About Us` when viewed in the app
- Visit your application on the `rentals` page and see what has changed. Try out the link - what happens?


## What are JavaScript objects?

Objects in JavaScript are a piece of information that allows us to group related info together.


In Ember most things that we work with revolve around objects. An object is defined by having zero, one or several _properties_, where each property has a specified value. An object can look for example like this:


```js
{ name: 'Marie Curie',
  job: 'Physicist',
  birthyear: 1867 }
```

The object allows us to store related information together one single piece of data. Similarly to Strings (words, e.g. 'pineapple') and Numbers (numbers, e.g. 42), objects can also be stored via variables. We can e.g. save the object above with the variable `scientist` as follows:


```js
let scientist = {
  name: 'Marie Curie',
  job: 'Physicist',
  birthyear: 1867
};
```


An object and its properties can be updated as follows:

```js
let scientist = {
  name: 'Marie Curie',
  job: 'Physicist',
  birthyear: 1867 };

scientist.name = 'Marie Skłodowska Curie';
console.log(scientist);
/*  This will log to your console the updated object:
{  name: 'Marie Skłodowska Curie',
  job: 'Physicist',
  birthyear: 1867  };
*/

```

## What is an Ember Object?

EmberObjects are a specific type of object. They come with many different features that native JavaScript objects which we learned about in the previous section don't have. In the scope of this workshop we won't be able to cover the special things an EmberObject can do versus a normal object, but we want to take a look on how to create one and be able to recognize it later on in the course.

Learning about the EmberObject is also important for knowing that almost everything we create in an Ember app is based on an EmberObject. We'll come back to that notion later during the course.

You can create an EmberObject as follows:


```js
import EmberObject from '@ember/object';

let programmer = EmberObject.create({
  title: 'Ada Lovelace',
  birthyear: 1815,
});

```


### Exercise 3c: Creating and passing an EmberObject

In this exercise we want to create a new EmberObject which can be used in the `rentals` route which we created earlier. We will use the EmberObject to carry information that will be displayed on the rentals page.

- Open the file `app/routes/rentals.js` in your text editor
- import the EmberObject from the `@ember/object` package as seen above in the previous example. You can put the import statement at the very top of the file
- inside of the `model() {}`, create the EmberObject with your application's name (you can choose one) as the object's `name` property and a descriptive text as the object's `text` property
- indicate that you'd like to pass the object down to your route's template by using the `return` keyword. Example on using `return` with an example object `myobject`:

```js
model() {
  let myobject = EmberObject.create({
    /* FILL IN YOUR PROPERTIES */
  });
  return myobject;
}

```

- Revisit your about page in your browser by visiting `http://localhost:4200/about` and see what has changed now


## How are routes and templates connected?

Earlier we created a new route using the Ember CLI by typing `ember generate route rentals` into the terminal. This gave us two files, namely

- app/routes/rentals.js
- app/templates/rentals.hbs

In this part we want to take a look at how templates and route files are interconnected. You already returned data from your route file to a template in the previous exercise. But how is it displayed there?

### Exercise 3d: Update information on the page

- Open `app/templates/rentals.hbs` and find all the properties of your `model` that are displayed
- Go back to `app/routes/rentals.js` and take a look: How can you make the listing mention that the rental is located in `Berlin` rather than San Francisco? Update the data returned from the `model` function in your route accordingly. Check back on the rentals page in your browser to see the change
- Investigate the `app/templates/rentals.hbs` template another time and take a look at the `availabilityStatus` which is currently not displayed in your app's rentals page. Find out how you can make the rentals page say, that the availability for this rentals is `for sale`
