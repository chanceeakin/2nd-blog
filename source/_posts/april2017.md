---
title: April 2017
date: 2017-04-13 18:26:38
tags:
comments: true
subtitle: Spring in Texas
cover_index: ../images/april.jpg
---

# Time flies.

It has been entirely too long since I wrote anything! The world got busy, and it dragged me along with it. So, I suppose I should recap my adventures.

## What I've been working on
1. Created a new version of my portfolio in React/Redux with Material Design
2. Created a VR application using Aframe/React. It takes from Twitter users' tweets
and renders them in VR.

## Portfolio

When I wrote my last blog entry, I was working on building my portfolio! Here it is:

[My Portfolio](https://chanceeakin.io)

A non-exhaustive list of the tech I used:
*  React MD (The view library upon which this is based)
*  Let's Encrypt for HTTPS encryption
*  The usual suspects and buzzwords

I'm a huge fan of minimal, archetypal design. Material Design in particular. So when I found out that there was a React/Redux port of Google's flagship Design paradigm, I had to jump on it! It's a great way to learn and quickly iterate using sound design principles, as well as play with some exciting Javascript technology. Let's dig in:

#### The Business

React MD is built in Javascript, namely ES6, and it takes advantage of the newer parts of the language. It also incorporates most of the cooler stuff about Redux: functional programming, modular code, etc.  The semantic organization of stylesheets wth container components is awesome, and adds for some painless visual grepping. All in all, a really cool set of tools. A set of tools I really didn't know how to use, until I built the thing. Hell, I still wonder if I actually know React/Redux.

The big pain point was when I made a redux cycle for checking window size. I wanted a different nav menu based on window width. In order to do that, I had to create an action, make it some reducers, hook it into the store. You know, Redux it up. The underlying cause of difficulty for me was application state (which differs substantially from react's state). Application state is the data your application uses data over time. I think we underemphasize the difficulty of understanding that concept, so here's my attempt at it.

Have you ever watched Interstellar? (SPOILER) Assuming you have, in the scene where Matt's character is in the dimensional representation of time (aka, the tesseract), he interacts with different snapshots of his daughter's room. Same room, different time. This is application state. Our data is like the dust, the books, the watch. We use some functions to move the data. The room stays the same. It's the only representation that makes sense to me. We use all the collected actions, reducers, and stores to create new snapshots of time. Without the snappy robot.

Once I figured out application state, a lot of the underly React/Redux infrastructure clicked, and voilà! A working, resizable menu.

## My VR application

My best friend from highschool is now a high school economics teacher, so I'm headed to speak to some kids in a week or two about code and about life. I thought that while I'm there, I could show them something fun. Since I'd been meaning to work with AframeVR, here's a follow up from earlier.

#### The Business

It got more difficult when I started using and building Aframe components. Aframe is fantastic, but it has some limitations--if only in terms of what it offers out of the box. In order to expand the power of the VR wrapper, it helps to know some three.js. In this case, I didn't have a grid component, so I wrote one. It was a wrapper to initialize a three.js element, like so:

```Javascript
if (typeof AFRAME === 'undefined') {
  throw new Error('Component attempted to register before AFRAME was available.')
}

AFRAME.registerComponent('trongrid', {
  schema: {
    size: {default: 10},
    divisions: {default: 10},
    colorCenterLine: {default: '#bada55'},
    colorGrid: {default: '#bada55'}
  },
  init: function () {
    var scene = this.el.object3D
    var data = this.data
    /* populates the three.js layer with registered data or defaults from schema. */

    var geometry = new THREE.GridHelper(data.size, data.divisions, data.colorCenterLine, data.colorGrid)
    scene.add(geometry)
  },
  remove: function () {
    var scene = this.el.object3D
    scene.remove(scene.getObjectByName('trongrid'))
  }
})
```

Fun, right? The first few lines check for Aframe, and the `registerComponent` portion creates a composable grid element. I wanted it to look like Tron, dammit. Here's where things get fun. React adds an extra layer of difficulty to implementing Aframe successfully, mostly because of how node modules need to imported. As it turns out, someone else wrote a better (ie, already published) npm package for an `aframe-gridhelper-component`, so I used that one instead. All that work for ~~nothing~~ learning. The crux of the matter: I couldn't get the component to change color. When working with React, the syntax for dealing with `<a-entity>` becomes `<Entity />`, among others. Here's what I mean.


##### Vanilla Aframe
```html
<a-entity gridhelper="size: 100; divisions: 100; colorCenterLine: black; colorGrid: black;"></a-entity>

```

##### React Aframe
```HTML
<Entity
  gridhelper={{size: 100, divisions: 100, colorCenterLine: "rgb(90, 229, 252)", colorGrid: "rgb(90, 229, 252)"}}
/>
```

See the difference? I don't want to tell you how long that little distinction took me to figure out. Hint: not. short. After fighting with Webpack to proxy my API server layer into the fun, the whole thing went off smoothly! [Repo is here: vr-data-visualizer](https://github.com/chanceeakin/vr-data-visualizer).

### Conclusion

Easter's coming up soon, and incidentally, I've been training for a Tough Mudder in May! Stay tuned for pictures!
