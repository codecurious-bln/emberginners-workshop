---
title: Step 7
order: 7
---

## How are components created?

To generate a new component, you can use the Ember CLI to create the required files. Think of a name for your new component, e.g. `my-component` and pass it to the `generate` command as follows:

```
ember generate component my-component
```

This will generate both the `.js` and the template `.hbs` file in your `app/components` and `app/templates/components` directory. Similar to a route, both the `.js` and the `.hbs` file are connected. Let's check this out in the next example.


### Exercise 7a: Create a Component

- In your terminal, use the Ember CLI to create a new component called `list-filter`
- Save the file and now invoke your component on the rentals template: `app/templates/rentals.hbs`
- What do you see on the rentals page?


### Computed properties

Computed properties are properties which may change over time. In an Ember app, they're often used whenever we aim for either user interaction or live updates to trigger a change in the display of our app. Computed properties allow automatic changes by depending on one to several other properties, that may change through user interaction and other events. We will see how this plays out in a later exercise. For now, let's see how a computed property is defined.

Let's try to create a computed property on an EmberObject by first defining two simple properties that might change during the lifetime of our application. Let's call them `greeting` and `name`:


```js
import EmberObject from '@ember/object';

export default EmberObject.extend({
  greeting: 'Aloha',
  name: 'Jen',
});
```

Let's now try to create a property that will always display both the greeting and the name as a full sentence. We could write something as follows:

```js
import EmberObject from '@ember/object';

export default EmberObject.extend({
  greeting: 'Aloha',
  name: 'Jen',
  fullGreeting: 'Aloha Jen!',
});
```

This comes with the disadvantage that any time we want to update the greeting phrase or the name, we'd also need to update the `fullGreeting` property ourselves to make the wording match. Using computed properties, we're able to let Ember do this for us automatically. You can define `fullGreeting` as a computed property as follows:


```js
import EmberObject, { computed } from '@ember/object';

export default EmberObject.extend({
  greeting: 'Aloha',
  name: 'Jen',
  fullGreeting: computed('greeting', 'name', function() {
    return `${this.greeting} ${this.name}!`;
  }),
});
```

The same principles apply to any descendant object of an EmberObject (components, routes among others). If we created an `ember-core-team-member` component that also had the same `fullGreeting` property as the EmberObject above, we could write:


```js
import Component from '@ember/component';
import { computed } from '@ember/object';

export default Component.extend({
  greeting: 'Aloha',
  name: 'Jen',
  fullGreeting: computed('greeting', 'name', function() {
    return `${this.greeting} ${this.name}!`;
  }),
});
```

In Ember you can always retrieve the value of a property on an EmberObject or any of its descendant objects like Components, Routes and others via `this.` when you're trying to get the value on the object itself. It means that you're looking for a property that is defined on *this* object. In the example above, we try to get a hold of the `greeting` and the `name` property inside of the `fullGreeting` property, which is also part of the same EmberObject, component or route. Therefore `this.greeting` and `this.name` will give us the properties of the same object.


#### Exercise 7b: Complete the computed property in the filter-list component

The filter-list component already comes with a `filterLabel` property, that needs to be completed

- Open your filter-list component's `.js` file
- Complete the content of the `filterLabel` computed property, so that it will always read `You have selected: <the filter name>`. Feel free to check out the template of the list filter component at `app/templates/components/list-filter.hbs` to see which property you have to set!
- This component needs to be dependent on the `selectedFilter` property to update correctly. You can set `selectedFilter` as a simple property for now and we will check out how to update the property later
