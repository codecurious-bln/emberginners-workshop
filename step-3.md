# An Intro to Routing in Ember

## What is routing?

Our application allows us to navigate different parts of it via url. The url is the name of a sub page in our website, which we can type into the browser navigation bar to allow us to land on that part of our app. The url allows to access different `routes` of our Ember app.

Routing in web applications is important, since it enables users to share a specific part of the app with others. E.g. if you want a friend to take a look at your super-rentals overview page, you can just send them the link (a.k.a url) that opens that part of the application.

To create routes that can be accessed via certain urls, we use the Ember CLI and more specifically its **generator** s. Using the `ember generate` command we can create all kinds of things in our application, including routes.

<!--
- Exercise: Generate a Route (‘about’). What is a route? Investigate new page in browser.
- Exercise: Copy-paste template into route. Observe server reload and page in the browser.
- Primer: Objects in JavaScript. What are values and properties?
- Ember Object Model. What is an EmberObject, how does it look like? -->


### Exercise: Generate a new route in your Ember app

- Open your terminal
- Type in `ember generate route about` and hit enter. Ember CLI will create several JavaScript files for you and edit some of them automatically for you. Check out the changes in these files in your text editor!
- Open `app/router.js` and investigate the newly added route: `this.route('about')`
- Open your application in your browser to see the new route in action: `http://localhost:4200/about`
- In our app, a route is represented by a JavaScript file (`.js` file ending) and a template (`.hbs` file ending). Open the template `app/templates/about.hbs` in your text editor
- Copy-pasta the following into your template (`app/templates/about.hbs`)

```hbs
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

- Save the file `app/templates/about.hbs` and go back to your app in the browser. What changed?



## What are JavaScript objects?

Objects in JavaScript are a special kind of data type. Each data type in JavaScript comes with its own characteristics in how you can store and access data. Data can come in many forms. E.g. the word 'tomster' in a JavaScript program can be a piece of data. If you wanted to use the word `tomster` in your JavaScript code, you'd need to do so using the `string` data type for example.


In Ember most things that we work with revolve around objects though. An object is defined by having no, one or several properties, where each property has a specified value. An object can look for example like this:


```js
{ name: 'Marie Curie',
  job: 'Physicist',
  birthyear: 1867 }
```

The object allows us to store related information together one single piece of data. Each property can be updated as follows:


```js
{ name: ... }

```
