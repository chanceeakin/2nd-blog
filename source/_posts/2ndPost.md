---
title: Holiday Cheer!
date: 2016-12-22 15:50:38
tags:
comments: true
subtitle: Christmas Parties and VR!
cover_index: ../images/secondPost.jpg
---
Well, we made it to the in-laws! Unlike most folks, I actually enjoy my in-laws, so this will be a nice break. Life is good, and I feel fortunate to be where I am. It's a lot of fun to see family, but it's not so fun to be a Texan in the Midwest. It's cold up here, y'all.

Okay, so now to React and VR. React recently dropped the prerelease of React VR, a combination of their React, React-Native, and now--a VR ecosystem, but I've yet to dig into that system enough to write about it with any form of eloquence. Instead, I've been making do with the Aframe-React package. It works really well, and it's been designed by Kevin Ngo. *[Repo Here](https://github.com/ngokevin/aframe-react)*

### Aframe-React
Aframe is also a wrapper around Three.js...which is a wrapper around WebGL. A fair amount of obfuscation, but I'd rather do fun things than try to remember an inordinate amount of math from high-school. Ha! I'd tell you that Aframe-React doesn't have enough components, but Kevin's the primary developer for Aframe as well, so...papa knows best. Aframe-React presents us with two real components:

#### `<Scene/>`
Scene functions as a wrapper around `<a-scene>`. Pretty much just set up. Don't include it, and you break things.

#### `<Entity />`
`<Entity/>`, on the other hand, is where most of the magic happens. Pass a few variables as `props` in the system, and voilà! Here's an example of how to make a 'primitive' (aka, a box):

```
<Entity
	animation__rot={{property: 'rotation', dur: 2000, loop: true, to: '360 360 360'}}
	animation__sca={{property: 'scale', dir: 'alternate', dur: 100, loop: true, to: '1.1 1.1 1.1'}}
	geometry='primitive: box'
	material={{color: 'red', opacity: 1}}
	position='0 -0.5 -3'
</Entity>
```

The above example comes verbatim from Kevin Ngo's *[Boilerplate](https://github.com/ngokevin/aframe-react-boilerplate)*. Let's look closer at what it does.

#### Animation
Each of the animation props give us...animation. The property designates the type of animation; loop, duration, and to provide additional details for the animation.

#### Geometry
Geometry gives us the 'primitive' object, a box. It gives us the actual object.

#### Material
Material designates what goes on the object. It can be a color, or it can be a texture...or a jpeg. Oh man, I had some fun with putting various jpegs on spinning cubes. Long story short, I'm childish.

#### Position
This places the object within your universe. Together, all of these things give you...

### A Cube!

![](../images/vr.jpg)


### Conclusion
So that's that! Kidding, there's so much more you can do with this tech, and I've only scratched the surface. I'm currently working on building an HTML Canvas/Aframe implementation, then porting it over to this React environment. While I'm doing that, I will be eating a fair amount of pie and all the Christmas cookies I can find. Happy Holidays, everyone!
