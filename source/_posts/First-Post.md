---
title: The First Post
date: 2016-11-03 22:07:52
tags: life
comments: true
subtitle: Welcome to the inside of my mind
cover_index: ../images/firstPost.jpg
---

This is my first post! I finally spooled up a blog, and now I have the time to tell you about myself. I could give you a lengthy diatribe on who I am, but all that will come in time. For the first post, I'm going to tell you about how I made this blog.

### Selection

I went through several different options before I picked out Hexo. There were several things to consider, and I used the following criteria in my selection process. They are as follows:

#### My criteria:

1. Runs on Node.js.
2. Minimal database creation. I feel like being lazy.
3. Extensible and easily replaceable themes. I get bored, and I wanted maintainability and support for future laziness.
4. Deployment through my own server. I have a Digital Ocean Droplet (more on that in a later blog), and I wanted to be able to run this bad boy on it. What's the point of calling myself "Full Stack" if I can't demonstrate it?

### Ghost

I started with the requisite Google search: "Blog developer nodejs." The only thing that came up was Ghost, so naturally, I tried it. I didn't really like it, mostly because it's in alpha and things are broken. It's going to be a cool product, and I'll switch at some point, but while it's in alpha, that will make deployment and maintenance problematic.

Ghost runs Handlebars and Ember.js, which are awesome. If you know Vanilla JS, you know Ember, and Handlebars is built off of Mustache templates. Again, if you've used one templating language, you've used most of them. I haven't seen large differences in any of them (templating languages), but I also haven't used many of them in large scale production/to the nth degree.

Since I build in React at work, I didn't feel like learning Ember this week. So, no Ghost for now.

## Bringing us to... Hexo.

Hexo is a blog platfom built by [Tommy Chen](http://www.hexo.io), and it's pretty sweet. Hexo hits all of my requirements, save for being able to access the index.js (Node.js) file directly. If I need to add something, it's a little more complex than calling `import blank from 'blankity-blank`, but it runs quite well otherwise. I can import themes, and I can write and edit all of my blog posts in Markdown!

### Fun, Unexpected Features

#### Yaml
Hexo uses *[Yaml](http://www.yaml.org/start.html)* in most of its configuration files in lieu of the usual JSON. Haven't used it a lot thus far, and I'm really excited to dig more into it as I extend this blog out further. There's a lot of stuff going on under the hood in Hexo, and I haven't investigated a lot of it.

#### A Robust NPM Community
With over 100 well-maintained packages, there are a lot of things I can add to Hexo to extend and customize its functionality. I don't plan on deploying to Github Pages or Heroku, but it's nice to have the option at my fingertips.

#### A community of designers
There's a lot of extensible inspiration online, and there are a lot of awesome people sharing themes. My current theme is [Phantom](https://github.com/klugjo/hexo-theme-phantom), and I love its minimalism and conscious UI decisions.

#### CLI
Hexo uses a CLI to spin up blog posts. More information is available in their [docs](https://hexo.io/docs/). Check it out, and spin one up for yourself!

### On the Docket/In Closing

Feel free to check out this project's source at my [GitHub](https://www.github.com/chanceakin). See something that's terrible or misattributed, send me an issue and I'll fix it!

This weekend, I'm headed to the farm. Next week, I'll be talking about something I'm learning or working on, most likely: React, Mocha, or Sass (SCSS). Maybe about some BBQ, too. I am in Austin, after all.3

Until next time,
Chance
