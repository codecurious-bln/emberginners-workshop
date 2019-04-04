---
title: Step 5
order: 5
---

# What are actions?

Actions are ways to make interactions of a user with your application trigger changes in your application's UI and they're especially useful for Components.

So far, you've learned how parent components can accept properties by being set on themselves or being passed into them on a template, and how that component can use those properties from both JavaScript and its template.

But what about the opposite direction? How does data flow back out of the component to the parent? In Ember, components use actions to communicate events and changes. Technically, actions are functions in JavaScript. We'll see what functions are in the next section.


## Functions in JavaScript

Functions are a reusable unit of one or several instructions in JavaScript. You can define a function using the `function` keyword, followed by a free name, e.g. `myFunction` and parentheses `()` and curly braces `{}` wrapping the instructions that should be part of the function. A function could look as follows:


```
function myFunction() {
  alert('Hello World!');
  alert('Hello again!');  
}
```

You can call your defined function by using its name, followed by parentheses and the obligatory semi-colon:


```
myFunction();
```

What are functions good for? Functions help us to write less repeatable code. In the example above we can e.g. save one line of code each time we call myFunction. We can call `myFunction` as often as we want by only writing a single line of code. It makes it also easy for us to update in our codebase. There's only one definition of `myFunction` and once we have updated it, we're able to update its invocations in several, other places of our code base automatically.

Even better, we can make functions also change their behavior each time we call them in dependance of **parameters**. A parameter is any value, e.g. a word or a number or an object, that we pass into the function via its parentheses. Going back to the function definition, we can make the function aware, that it requires and uses parameters by including it in its function definition:


```
function myFunction(planet) {
  alert(`Hello ${planet}!`);
  alert(`Hello again!`);    
}
```

### Exercise 5a: Call a function

- Open your browser and its console as described in step 1
- copy-pasta the function definition for myFunction into your console and hit enter
- Your function is now available in your browser to be called anytime. Try to call the function with a word of your choice and see what happens
- Try calling the function with another word, what happens now?

## Binding actions

In Ember, an action is special kind of function. An action can be bound to components and UI elements to be triggered with user interaction. An function can be added as an action to e.g. a component by adding it to the `actions` object as follows:


```
// app/components/my-component.js
import Component from '@ember/component';


export default Component.extend({
  actions: {
    myFunction() {
      alert('Hello World!');
    }
  },
});

```

In this example we omitted the `function` keyword as we have defined it on an object directly. The writing style of `myFunction() {}` is in fact a short hand for `myFunction: function() {}`.


An action can be bound to any element or a component. For e.g. an ready-to-use input component, we can write the following to bind the action defined in `my-component`:

```
<!-- app/templates/components/my-component.hbs
{{input key-up=(action "myFunction")}}
```

Anytime the user types into the input (which will trigger a `key-up` event) the action `myFunction` is called.


### Exercise 5b: Create an action in the list-filter component

- open your `app/components/list-filter.js` file and add an action
- Update the action definition for the `handleFilterEntry` action by filling it in with the following instruction:

```
alert(`Hello World!`);
```
- Go back to your rentals page in your browser and try interacting with the list filter. What happens?
- Attach the action correctly to the input field by updating your component template for the list filter
- Try again in your browser. What happens now?
- Try filling in the following functionality into your `handleFilterEntry` action instead
```
let filterInputValue = this.value;
let filterAction = this.filter;
filterAction(filterInputValue).then((resultsObj) => {
  if (resultsObj.query === this.value) {
    this.set('results', resultsObj.results);
  }
});
```
