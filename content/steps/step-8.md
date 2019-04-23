---
title: Step 8
order: 8
---

# What are Arrays?

**Arrays** in JavaScript are another kind of **data type**. You can imagine an array to be a list of different items and it can list about anything: numbers, strings ("words") and even objects or other arrays.

Arrays are always useful if you want to group several related things together. We will see how we can use arrays in some code examples.

## Creating an Array

You can create an array by assigning it to a variable:

```js
let list = [];
```

This will create an empty array. If you checked `list` for it's value by e.g. logging it to your console, it'd say:

```js
console.log(list);
// => []
```

When creating an array, you can already fill it with a collection of anything at the same time. Let's for example create a list of fruits in the form of an array as follows:

```js
let fruitbasket = ['cherries', 'apples', 'grapes', 'strawberries'];
console.log(fruitbasket);
// => ['cherries', 'apples', 'grapes', 'strawberries']
```

Creating arrays with other types of data works in a very similar way. You can create an array containing objects like this:

```js
let scientists = [{ name: 'Marie Curie', job: 'Chemist'}, { name: 'Ada Lovelace', job: 'Computer Scientist' }];
```

Or an array containing numbers like that:

```js
let lottery = [12, 21, 34, 48, 2, 1];
```

By the way, you can also mix and match:

```js
let allthethings = [{ name: 'Eeyore', kind: 'donkey' }, 12, 'cherries', 3];
```

## Interacting with Arrays

There are many different ways to interact with arrays and make use of the fact, that they contain a collection of items in an ordered manner. In the scope of the tutorial, we won't be able to give a full overview of all the different ways to work with arrays, but please feel free to take a look [at this great introduction in your own time after this course]().

Instead, in this workshop we will show you one neat function that you can use right from the start on each array. It allows you to go through each single of its contents and do something with it, for example log it to the console or really anything that you can come up with. This function is called `forEach` and you can use it as follows:


```js
fruitbasket.forEach(function(fruit) {
  console.log(fruit);
});
// => cherries
// => apples
// => grapes
// => strawberries
```

When we call `forEach` on the array and pass it a function which we **freely define ourselves** (see `function(fruit) { console.log(fruit); }`) we will now log, one after each other, every single fruit item that is contained inside of `fruitbasket`,

In the next exercise, try `forEach` out for yourself and see what happens!

### Exercise 8a: Loop over an array

- Open your browser and the developer console
- Create an array listing a several objects. Each object should define the name of one of your table neighbours, as well as the operating system they're using. E.g. if the person  sitting next to you is called Suzie and is using a Mac, create an object as the following:

```js
{ name: 'Suzie', os: 'Mac' }
```
- Fill the array with objects defining all your table neighbours
- After creating the array, use the `forEach` function to log a message that reads as follows `Suzie is using a Mac` for each of the list items. You can adapt the following template to log it in your console message:

```
`${someone} is using a ${os}`
```

Be sure to replace `someone` and `os` with the correct variable names that are provided to your function. Remember that each time `forEach` is called you're dealing with an object - reflect how to look up the values you need!


## What are Enumerables?

In an Ember app, an enumerable is a special kind of object, that contains any number of other objects - so called child objects. Ember allows you to interact with enumerables in a similar way as you would do with generic JavaScript arrays, but on top of that also provides with additional helper functions and properties that are unique to Ember's enumerable.

In the scope of this workshop we want to take a look how you can interact with enumerables in your application and specifically in the template. To learn more about that, let's take a look at one particular and very handy helper: `each`


## How does the each template helper work?

In our templates we have the ability to not only invoke components we have built ourselves, but also to use a couple of very useful built-in helpers, that Ember provides us with right from the start. One of these helpers is each. It allows us to go through each item of an enumerable - a list of objects - and do something with them in our template. In this regard it is in fact very similar functionwise as the `forEach` function we got familiar with in the previous exercise.

Instead of being able to do something with the list items in the context of a self-defined function though, the `each` helper allows us to do something with the list items **directly in the template** instead. Check out this example template:

```hbs
{{#each fruitBasket as |fruit|}}
  {{fruit}}!
{{/each}}
```

If `fruitBasket` happens to be an enumerable listing the same fruits as the `fruitbasket` array from the section before, it will render in our page as:


```
cherries!
apples!
grapes!
strawberries!
```

Pay attention to how the enumerable's items are provided to the template: the `each` helper allows you to define a new variable name for the list's items that you will use for reference further down the template in the each helper's so-called **block** - the section that is between the opening of the each section (`{{#each}}`) and its closing (`{{/each}}`). In the example above we defined the variable name of the items in `fruitBasket` to be `fruit` in the block. But the following code would have also worked in the same way:


```hbs
{{#each fruitBasket as |somethingelse|}}
  {{somethingelse}}!
{{/each}}
// => cherries!
// => apples!
// => grapes!
// => strawberries!
```

### Exercise 8b: Display all the rentals

So far we have only displayed one single rental at a time in our super rentals app, but this will change in this exercise! The app has been updated to already provide a list of several rentals to the template. You can retrieve the list of rentals in your template via the variable `model`. `model` holds the enumerable that contains the objects definining the rentals to be displayed on the page.

- Revisit the template for the rentals page `app/templates/rentals.hbs`
- Replace the missing parts so that you're able to display all the rentals that are passed to the template as `model`. Be sure  to make use of the `rental-listing` component you are already using to display a single rental to your advantage!
- Check back in your browser at `http://localhost:4200` - what do you see?

### Exercise 8c: Filter your rentals list by city

Your Ember demo app is automatically updated at this step to let your `list-filter` component have a new functionality. Be sure to checkout the component definition at `app/components/list-filter.js` to check out the changes. In the following make sure that your list filter integrated with the rentals list well as follows:

- Bind the new action that has been add to the `list-filter` to the input field found in the component's template. Check out   the component definition to figure out its name. Also remember that actions that are bound inside of helpers or components are wrapped into parentheses (`()`) and not into curly braces (`{{` `}}`) as we've seen in earlier examples
- Go back to the rentals page template and notice how the `ListFilter` component wraps the `RentalListing` component and gives back an object `filteredResults`. This is in fact an enumerable that will be updated automatically once you use the list filter. Remember the exercise using `each` before and imagine how you could use the `filteredResults` list as part of your rentals list which is **inside of the ListFilter block**
- After you made  your changes, go back to the rentals page and try to use the filter. What do you see?
