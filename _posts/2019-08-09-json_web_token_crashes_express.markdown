---
layout: post
title:  "Token Gesture"
date:   2019-08-09 22:30:00 +0000
categories: blog
---
## JSON Web Token Crashes Express

It's been a little while since I'd run through building an Express API up from scratch, so wanting a bit of mental exercise, I pulled out one of my [GA](https://generalassemb.ly) lessons and fired up VS Code. All the packages I needed were installed manually at the CLI; [Express](https://www.npmjs.com/package/express), [Mongoose](https://www.npmjs.com/package/mongoose), [Morgan](https://www.npmjs.com/package/morgan), [body-parser](https://www.npmjs.com/package/body-parser), and what have you. Initially all tested out OK in [Insomnia](https://www.insomnia.rest/), I could register new users, login, and hit endpoints as expected.

All ran well until I installed the [JSONWebToken](https://www.npmjs.com/package/jsonwebtoken) (JWT) package - (`$ npm install jsonwebtoken --save`) - at which point any attempt to register a user or login crashed `nodemon` and spit out an error along the lines of

```cli
events.js:167
      throw er; // Unhandled 'error' event
      ^

Error: Expected "payload" to be a plain object.
    at validate (/Users/christopherallanperry/development/express-api-jwt/node_modules/jsonwebtoken/sign.js:40:11)
```

Aside from requiring the package, the only other line of code to go into my API was this, which was a direct lift from what I'd used previously, but the error message did seem to be doing a fair bit of fingerpointing at the JWT `sign()` method, though it wasn't immediately obvious why.

```js
const token = jwt.sign(user._id, config.secret, { expiresIn: 60 * 60 * 24 });
```

Checking back on the old and new `package.json` files I noticed that they were using different versions of the JWT package - the old was on v7.1.9 and the new a major version up at v8.5.1. Reverting the new `package.json` file back to v7.1.9 immediately got me a functioning API again, with JWT tokens being generated both on a new user being created, or when they were logged back in again. OK, so definitely an issue with the changed package versions then.

Heading over to NPM and the [jsonwebtoken page](https://www.npmjs.com/package/jsonwebtoken) I spotted a telltale link under the migration notes section - [From v7 to v8](https://github.com/auth0/node-jsonwebtoken/wiki/Migration-Notes:-v7-to-v8) which said the JOI validation library had been removed, which impacted on the way `sign()` worked. Seemingly, this was to reduce the overall size of the JWT package itself, as it was getting a little bloated.

Checking back over the example implementations for `sign()`, it became apparent that there was a difference in the way in which the payload (an object in itself) was being presented to the method, it now having an object wrapper around it. A quick edit to the line of code setting up the token, and having re-installed the v8.5.1 package, the API was back up and running again.

```js
const token = jwt.sign({ data: user._id }, config.secret, { expiresIn: 60 * 60 * 24 });
```

Lesson learned then, just because it worked once, don't assume it will work as expected next time.
