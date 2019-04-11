---
title: Step 7
order: 7
---

## What are Addons - Part 2?

### Exercise 6b: Installing Ember addons - Ember Leaflet

To be able to display a map in our rentals page we can add an addon called Ember Leaflet

- Check out Ember Observer and try to find the addon details page for Ember Leaflet
- Install the addon in your Ember app according to the instructions on the page
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
