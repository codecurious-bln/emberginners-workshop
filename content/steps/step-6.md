---
title: Step 6
order: 6
---

# What are Addons?

Ember addons are plugins for your Ember app that are created and maintained by the community and which provide you with free to use functionality for your app, including new themes, components, functions and much, much more. You can install any Ember addon that you can find on [Ember Observer](https://emberobserver.com/) by using the `ember install` command. If we, for example, wanted to install the popular Ember addon `ember-simple-auth`, we could type into our terminal while in our app directory

```
ember install ember-simple-auth
```

This would automatically add the Ember addon to our application and preconfigure it. Depending on the addon we can use it in different ways. In the following example, we're gonna install and use and Ember addon to add a map view to our Ember app.


### Exercise: Installing Ember addons - Ember CLI Tutorial Style

First let's add some styling to our Ember application. You can install the addon `ember-cli-tutorial-style` to make your app shine in an instant

- Install in your app directory via `ember install ember-cli-tutorial-style`
- Quit your serve by pressing `Ctrl + C` (Windows + Linux) or `Command + C` (Mac) in your terminal window where your server is running
- restart the server by typing `ember server` and hitting enter
- Revisit your Ember app in your browser. What do you see?

### Exercise: Installing Ember addons - Ember Leaflet

To be able to display a map in our rentals page we can add an addon called Ember Leaflet

- Check out Ember Observer and try to find the addon details page for Ember Leaflet
- Install the addon in your Ember app
- Copy-pasta the following configuration into your `mirage/config` file:

```
this.passthrough('https://api.mapbox.com/**');

```

- Get an access token for your map over [here](https://www.mapbox.com/account/access-tokens/)
- Quit your server and restart it again, this time using the following command:

```
LEAFLET_MAPS_API_KEY=<your key here> ember s

```
- Go back to your app in your browser and investigate the rentals page. What is happening now?
