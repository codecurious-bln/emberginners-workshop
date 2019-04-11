---
title: Step 5
order: 5
---

# An Intro to Components in Ember

## What is a Component?

A component is an EmberObject that can be used to display interactive content in your Ember application. Ember components are used to turn markup text and styles into reusable content. Components consist of two parts: a JavaScript component file that defines behavior, and its accompanying Handlebars template that defines the markup for the component's UI.


## Where Can I Find Components?

Components that have been created as part of our application can be used in any page of our application. You can find components that are already part of this application by taking a look into the `app/components` folder. You might e.g. see the following:

```
- app
  |-- components
      |-- my-component.js
```

## How Can I Use Components?

You can use a component by typing its name in [upper camel case](http://wiki.c2.com/?UpperCamelCase) anywhere in a page's template.
We could add that component created in `app/components/my-component.js` to the rentals page as follows:


```
<!-- app/templates/rentals.hbs -->
<MyComponent />
```

This process is also described as _invoking a component_. Once the component is invoked, we can check back to the `about` page in our browser and see the component displayed right where we left it in the template - after the page's title, but before its descriptive text.


### Exercise 5a: Invoke the rental listing component

s described in the previous section Ember applications keep components in one single place. Check out your own application for the presence of components using the terminal. Which components are there? Keep in mind that you can use `cd` to move between folders and `ls` to list the content of a folder.

- Open your application's template for the `rentals` page
- Invoke the component that you already found in your app in `app/templates/rentals.hbs`
- View your rentals page in the browser and see what happened. Attention! You can now access your `rentals` page by visiting your home page at [http://localhost:4200/](http://localhost:4200/)


## What are component properties?

Since Ember components are a special type of EmberObjects, which in return are a special type of JavaScript objects, Ember Components also have properties just like any object. What's special about EmberObjects and components though, is that they can have two different types of properties: regular properties and computed properties.


### Regular Properties

Regular properties can be defined on your component directly in two different ways:

- Setting a component property in its respective `.js` file. We can e.g. set a title property on the following component as such:

```
// app/components/my-component.js
import Component from '@ember/component';

export default Component.extend({
  title: 'My new component',
});
```
This works exactly was we would expect when declaring a property on a regular JavaScript object. Feel free to take another look at [Step X](#url) for another refresher.

- Or by passing the property into the component right where it is invoked in a template:

```
<!-- app/templates/another-route.hbs -->
<MyComponent @title="My new component" />

```

Later on, this property is available in our component template at `app/templates/components/my-component.hbs` as such:


```
<!-- app/templates/components/my-component.hbs -->
{{this.title}}
```

Once we invoke our component in a route and visit that route in our browser, we can see the title displayed right where the component is put into the page.

#### Exercise 5b: Change the component view with properties

- Open your `app/components/rental-listing.js` and see which properties are already available. What do you find?
- Take another look at `app/templates/componets/rental-listing.hbs` - what do you find when you're thinking about the properties that you already found defined in the `rental-listing.js` file?
- Investigate the UI of the rental-listing component in your browser on your `rentals` page
- Go back to `app/templates/rentals.hbs` and pass in the property that is responsible for the image width with the value `true`
- Re-investigate the `rentals` page in the browser. What has happened?

### How can you manipulate properties otherwise?

Passing in a value at the invocation site of a component is not the only way to update component property values. You can also use `.set()` to change property values.


```
let programmer = EmberObject.create({
  title: 'Ada Lovelace',
  birthyear: 1815,
});
console.log(programmer.birthyear);
// => 1815

programmer.set('birthyear', 1817);
console.log(programmer.birthyear);
// => 1817
```

There's a special functionality you can use for flipping between a special kind of value: Booleans. Boolean values can only have one of two different states: `true` or `false`. To update Booleans, you can also use `.toggleProperty()` to change the value to the opposite.

```
let programmer = EmberObject.create({
  title: 'Ada Lovelace',
  birthyear: 1815,
  isScientist: true,
});
console.log(programmer.isScientist);
// => true

programmer.toggleProperty('isScientist');
console.log(programmer.isScientist);
// => false

programmer.toggleProperty('isScientist');
console.log(programmer.isScientist);
// => true
```
