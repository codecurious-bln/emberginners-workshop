---
title: Step 9
order: 9
---

## Where to find addons?

When developing Ember apps, addons always come into handy to add new functionality to your application by relying on sound community solutions. Your best bet for discovering Ember addons and find out more about how to use them is [Ember Observer](http://emberoberserver.com). In the following exercise, we'll learn how to use Ember Observer to add an addon that helps us build out a street map for our rental listings.

### Exercise 9a: Installing Ember addons - Ember Leaflet

To be able to display a map in our rentals page we can add an addon called Ember Leaflet

- Check out Ember Observer and try to find the addon details page for Ember Leaflet
- Install the addon in your Ember app according to the instructions on the page
- Get an access token for your map over [here](https://www.mapbox.com/account/access-tokens/)
- Quit your server and restart it again, this time using the following command:

```
LEAFLET_MAPS_API_KEY=<your key here> ember s

```

## Adding a street map to our rentals page

In this part of the workshop we want to finally display a street map of our rental's location next to its listing. Up until this point of the course the app has been automagically updated to provide a new component that is based on the `ember-leaflet` addon that you've installed in the previous step.

### Exercise 9b: Add the street map to the rental listing component

- Find out which new component has been added to the application just now
- Invoke the new component in the template of the `rental-listing` component. The `REPLACE ME` placeholder indicates a good spot do so
- The new component accepts one argument called `@location`. Be sure to pass the `@location` argument to the component at its invocation site. The value that you should pass to `@location` is the **city** of the respective rental
