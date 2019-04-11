---
title: Step 6
order: 6
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
// => Hello World!
// => Hello again!
```

What are functions good for? Functions help us to write less repeatable code. In the example above we can e.g. save one line of code each time we call myFunction. We can call `myFunction` as often as we want by only writing a single line of code. It makes it also easy for us to update in our codebase. There's only one definition of `myFunction` and once we have updated it, we're able to update its invocations in several, other places of our code base automatically.

Even better, we can make functions also change their behavior each time we call them in dependance of **parameters**. A parameter is any value, e.g. a word or a number or an object, that we pass into the function via its parentheses. Going back to the function definition, we can make the function aware, that it requires and uses parameters by including it in its function definition:


```
function myFunction(planet) {
  alert(`Hello ${planet}!`);
  alert(`Hello again!`);
}
```

and calling it with a specific value by passing the parameter into the function as follows:

```
myFunction("Saturn");
// => Hello Saturn!
// => Hello again!
```

### Exercise 6a: Call a function

- Open your browser and its console as described in step 1
- copy-pasta the function definition for myFunction into your console and hit enter
- Your function is now available in your browser to be called anytime. Try to call the function with a word of your choice as a parameter (pass it into the braces `()`) and see what happens
- Try calling the function with another word, what happens now?

## Binding actions

In Ember, an action is special kind of function. An action can be bound to components and UI elements to be triggered with user interaction. Any function can be added to a component as an action.

First, if there isn't one yet, you need to add an `actions` object - or a so-called `actions` _hash_ - to your component:

```
// app/components/my-component.js
import Component from '@ember/component';


export default Component.extend({
  actions: {

  },
});
```



Next, you can define an action by adding a function with a specific name to that `actions` hash:


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
<button onclick={{action "myFunction"}}>Click me</button>
```

Anytime the user clicks the button (which will trigger a so-called `onclick` event) the action `myFunction` is called. Events are a way in JavaScript to tie in functionality that you have written in your program with a user interaction. There are many different events available such as `click`, `scroll`, `keyup`, `mouseenter`, among many others.


### Exercise 6b: Create an action in the rental-listing component

- open your `app/components/rental-listing.js` file and add an action called `toggleImageSize`
- If the action is called, the property `isWide` should be changed to the opposite value. E.g. if `isWide` has the value `true`, after calling the action it should turn out to be `false`. Calling the action while `isWide` is `true` should end up in `isWide` having the value `false`. You can review the [Step 5](x) for a quick refresher on what you can use to make the property flip between the `true` and `false` value
- Update the action definition for the `handleFilterEntry` action by filling it in with the following instruction:
- Try again in your browser. What happens now?
