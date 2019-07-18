---
layout: post
title:  "Setting up an ES6 Project Using Babel and webpack"
date:   2019-03-30 10:00:00 +0000
categories: blog
---
_This excerpt is taken from an article I wrote for Sitepoint which was published back in April 2018:_

**In this article, we’re going to look at creating a build setup for handling modern JavaScript (running in web browsers) using [Babel](https://babeljs.io/) and [webpack](https://webpack.js.org/).**

This is needed to ensure that our modern JavaScript code in particular is made compatible with a wider range of browsers than it might otherwise be.

JavaScript, like most web-related technologies, is evolving all the time. In the good old days, we could drop a couple of `<script>` tags into a page, maybe include jQuery and a couple of plugins, then be good to go.

However, since the introduction of ES6, things have got progressively more complicated. Browser support for newer language features is often patchy, and as JavaScript apps become more ambitious, developers are starting to use modules to organize their code. In turn, this means that if you’re writing modern JavaScript today, you’ll need to introduce a build step into your process.

As you can see from the links beneath, converting down from ES6 to ES5 dramatically increases the number of browsers that we can support.

- [ES6 compatibility](https://kangax.github.io/compat-table/es6/)
- [ES5 compatibility](https://kangax.github.io/compat-table/es5/)

The purpose of a build system is to automate the workflow needed to get our code ready for browsers and production. This may include steps such as transpiling code to a differing standard, compiling Sass to CSS, bundling files, minifying and compressing code, and many others. To ensure these are consistently repeatable, a build system is needed to initiate the steps in a known sequence from a single command.

## Prerequisites
In order to follow along, you’ll need to have both [Node.js and npm](https://nodejs.org/) installed (they come packaged together). I would recommend using a version manager such as [nvm](https://github.com/creationix/nvm) to manage your Node installation ([here’s how](https://www.sitepoint.com/quick-tip-multiple-versions-node-nvm/)), and if you’d like some help getting to grips with npm, then check out SitePoint’s [beginner-friendly npm tutorial](https://www.sitepoint.com/beginners-guide-node-package-manager/).

...the full article can be found at [Setting up an ES6 Project Using Babel and webpack](https://www.sitepoint.com/es6-babel-webpack/)


