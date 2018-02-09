---
layout: post
title:  "MEAN Stack: Building a VueJS Front-End onto a NodeJS API - Part 1"
date:   2018-02-08 16:00:00 +0000
categories: blog
---
## Background
A recently posted article on Sitepoint titled [MEAN Stack: Build an App with Angular 2+ and the Angular CLI](https://www.sitepoint.com/mean-stack-angular-2-angular-cli/) piqued my interest, having used Angular 1.5 on a couple of projects during my [GA WDI course](https://generalassemb.ly/education/web-development-immersive) down in London. A few days after it was published though, I attended the inaugural [VueJS-Manchester](https://www.meetup.com/VueJS-Manchester) Meetup hosted by the [MoneySuperMarket team](http://www.moneysupermarketjobs.com/careers/meet-the-team). Could I take a lead out of the Sitepoint article, but switch out the [Angular 2+](https://angular.io/) for [VueJS](https://vuejs.org/) I wondered? This blog post and its successor sets out to answer that question. In this first part, I'll look at building out the API with NodeJS, MongoDB and Mongoose, and the changes I made to it.

## GitHub Repo
You can find the code for this series on my [GitHub repo 'YATA'](https://github.com/christopherallanperry/yata). The article describes the application it sets out to create as an 'Awesome Bucket List Application', but we all know it's a TODO list, hence the repo name YATA (Yet Another Todo App). As a quick PSA, be aware that the repo is still undergoing further development as I start to build out the VueJS side of things - more on that though in Part 2.

## Changes to the Build
### Dependencies
I'm used to having the [morgan](https://www.npmjs.com/package/morgan) HTTP request logger as one of my dependencies, so that went in through the CLI with...
```cli
npm install morgan --save
```
I also included the [errorhandler](https://www.npmjs.com/package/errorhandler) middleware, but at this point, I'm unsure whether that's going to get used. If you want it though, install it as follows...
```cli
npm install errorhandler --save
```

### Config
For the most part, I followed the article to build out the API with NodeJS, Express, MongoDB, and Mongoose, with the API handling the M and C parts of an MVC pattern. I moved the content of the `database.js` file into `config/config.js` and added the port variable definition to it like so...
```js
const port = process.env.PORT || 3000;
const db = process.env.MONGODB_URI || 'mongodb://localhost:27017/bucketlist';

module.exports = {
  port,
  db
};
```
...and called it back into the main `app.js` file with a reworked dependency
```js
const config = require('./config/config');
```
There's no overriding reason to do this for this app at this point, but it does help declutter the `app.js` file a bit, and is a good place to put other config items, such as hash strings for security purposes, should you need those at a later date.

### Model Timestamps
I've added timestamps to the model in `list.js`, as knowing when items have been created/modified seems like something you might want to have, even if they're not used immediately.

### Additional End-Points
I've added in a couple of new end-points to go with those the article includes for the INDEX, CREATE and DELETE ones of a RESTful API. The new end-points are to provide options for SHOW and UPDATE options. The API's I've worked on previously have all kept the business end of each end-point in with their respective controller, however, this one has them in with the model. I did consider refactoring this, but in the end decided to stick with the pattern and see how it played out.

### SHOW end-point
For the `list.js` file, accessing a single list item ( for a GET request on `/bucketlist/:id` ), I added...
```js
module.exports.getListById = (id, callback) => {
  const query = { _id: id };
  BucketList.findById(query, callback);
};
```
...and for the `bucketlist.js` file
```js
router.get('/:id', (req, res, next) => {
  // access the parameter which is the id of the item to be deleted
  const id = req.params.id;
  // Call the model method deleteListById
  bucketlist.getListById(id, (err, list) => {
    if (err) {
      res.status(404).json({ success: false, message: `Failed to find the list item. Error: ${err}` });
    } else if (list) {
      res.status(200).write(JSON.stringify({ success: true, lists: list }, null, 2));
      res.end();
    } else
      res.status(400).json({ success: false, message: `Bad request. Error ${err}` });
  });
});
```
### UPDATE end-point
In `list.js` for updating by ID ( for a PUT request on `/bucketlist/:id` ), I added...
```js
module.exports.updateListById = (id, changes, callback) => {
  const query = { _id: id };
  BucketList.update(query, changes, callback);
};
```
...and in the `bucketlist.js` file, this...
```js
router.put('/:id', (req, res, next) => {
  // Access the id parameter
  const id = req.params.id;
  const changes = req.body;
  // call the model method updateListById
  bucketlist.updateListById(id, changes, (err, list) => {
    if (err) {
      res.status(400).json({ success: false, message: `Failed to update the list. Error: ${err}` });
    } else if (list) {
      res.status(200).json({ success: true, message: 'Updated successfully' });
    } else
      res.status(400).json({ success: false });
  });
});
```
### Status codes
Lastly, I added a `res.status()` to give appropriate HHTP status codes to each end-point.

## Testing
All the end-points were tested with my usual tool, the [Insomnia REST client](https://insomnia.rest/), and everything checks out OK.

For the moment then, we can call the API done. In Part 2, I'll look at getting VueJS set up and connected to the API, and take a closer look at how it works for a small scale application like YATA. See you next time.
<br>
<br>
