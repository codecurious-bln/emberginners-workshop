# An Intro to Components in Ember

## What is a Component?

A component is an EmberObject that can be used to display interactive content in your Ember application. Ember components are used to turn markup text and styles into reusable content. Components consist of two parts: a JavaScript component file that defines behavior, and its accompanying Handlebars template that defines the markup for the component's UI.



## How are Components used?

You can use a component, also described as "invoking" a component, by typing its name in double curly braces anywhere in the template. If e.g. we had a component called `my-component` in our application, we could add it to the about page as follows:


```
<!-- app/templates/about.hbs -->
{{my-component}}
```

Once the component is invoked, we can check back to the about page in our browser and see the component displayed right where we left it in the template - after the page's title, but before it's descriptive text.


### Exercise: Invoke Rental Listing Component

Your demo application already comes with a ready-to-use component pre-equipped. Its name is `rental-listing`.

- Open your application's template for the `about` page
- Invoke the `rental-listing` component on the `app/templates/rentals.hbs` template
- View your about page in the browser and see what happened


## How are Components Created?

To generate a new component, you can use the Ember CLI to create the required files. Think of a name for your new component, e.g. `my-component` and pass it to the `generate` command as follows:

```
ember generate component my-component
```

This will generate both the `.js` and the template `.hbs` file in your `app/components` and `app/templates/components` directory. Similar to a route, both the `.js` and the `.hbs` file are connected. Let's check this out in the next example.


### Exercise: Create a Component

- In your terminal, use the Ember CLI to create a new component called `list-filter`
- Open the file `app/templates/components/list-filter.hbs` and update its content with the following:

```
{{input
  value=this.value
  key-up=(action "handleFilterEntry")
  class="light"
  placeholder="Filter By City"
}}
{{yield this.results}}
```

- Save the file and now invoke your component on another route's template, that you can find on `app/templates/rentals.hbs`
- What do you see on the rentals page?


## What are Component Properties?

Ember Components have to different types of properties. Simple properties and computed properties.


### Simple Properties

Simple properties can be defined on your component directly in two different ways:

- Setting a component property in its respective `.js` file. We can e.g. set a title property on the following component as such:

```
// app/components/my-component.js
import Component from '@ember/component';

export default Component.extend({
  title: 'My new component',
});
```

- Or by passing the property into the component right where it is invoked in a template:


```
<!-- app/templates/another-route.hbs -->
{{my-component title="My new component"}}

```

Later on, this property is available in our component template at `app/templates/components/my-component.hbs` as such:


```
<!-- app/templates/components/my-component.hbs -->
{{title}}
```

Once we invoke our component in a route and visit that route in our browser, we can see the title displayed right where the component is put into the page.

#### Exercise: Adding A Title to List Filter

- Open your `app/components/list-filter.js` and define a `title` property
- Show the title somewhere in your component's template
- Investigate the UI in your browser on your `rentals` page
- Go back and pass in the same property on the component's invocation site with another word for the title
- Re-investigate the `rentals` page in the browser. What has happened?


### Computed Properties

Computed properties are properties which may change over time. In an Ember app, they're often used whenever we aim for either user interaction or live updates to trigger a change in the display of our app. Computed properties allow automatic changes by depending on one to several other properties, that may change through user interaction and other events. We will see how this plays out in a later exercise. For now, let's see how a computed property is defined.

Let's try to create a computed property on an EmberObject by first defining two simple properties that might change during the lifetime of our application. Let's call them `greeting` and `name`:


```
import EmberObject from '@ember/object';


export default EmberObject.extend({
  greeting: 'Aloha',
  name: 'Jen',
});
```

Let's now try to create a property that will always display both the greeting and the name as a full sentence. We could write something as follows:

```
import EmberObject from '@ember/object';


export default EmberObject.extend({
  greeting: 'Aloha',
  name: 'Jen',
  fullGreeting: 'Aloha Jen!',
});
```

This comes with the disadvantage that any time we want to update the greeting phrase or the name, we'd also need to update the `fullGreeting` property ourselves to make the wording match. Using computed properties, we're able to let Ember do this for us automatically. You can define `fullGreeting` as a computed property as follows:


```
import EmberObject, { computed } from '@ember/object';


export default EmberObject.extend({
  greeting: 'Aloha',
  name: 'Jen',
  fullGreeting: computed('greeting', 'name', function() {
    return `${this.greeting} ${this.name}!`;
  }),
});
```

In Ember you can always retrieve the value of a property on an EmberObject or any of its sibling objects like Components, Routes and others via `this.` when you're trying to get the value on the object itself. It means that you're looking for a property that is defined on *this* object. In the example above, we try to get a hold of the `greeting` and the `name` property inside of the `fullGreeting` property, which is also part of the same EmberObject. Therefore `this.greeting` and `this.name` will give us the properties of the same object.


#### Exercise: Complete the computed property in the filter-list component

The filter-list component already comes with a `filterLabel` property, that needs to be completed

- Open your filter-list component's `.js` file
- complete the content of the `filterLabel` computed property, so that it will always read `You have selected: <the filter name>`
- This component needs to be dependent on the `selectedFilter` property to update correctly. You can set `selectedFilter` as a simple property for now and we will check out its updates later
