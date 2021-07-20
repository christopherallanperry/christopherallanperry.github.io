---
layout: project
title: Free-the-Books
subtitle: Leave books in public spaces, then use our app to record its discovery by others, who'll leave it somewhere new and perpetuate the its journey.
heroku: https://fierce-fortress-98221.herokuapp.com/
github: https://github.com/christopherallanperry/WDI_PROJECT_3
repo_name: WDI_PROJECT_3
---

'Free-the-Books' came about as our group project. Having initially explored ideas around a dating or news app, we settled on the idea of creating an application that would provide a way of having people leave some of their favourite books in public spaces, with a randomly generated code inside them. Those finding the book could use the code on our app to record where the book was found and allow other's to trace the book's journey. In order to give the call to action some impetus, and after a lengthy brainstorming session, we settled on the notion of giving the book release process something of a revolutionary theme, hence the colour keyway used, and its imagery.

For this project, I was responsible for creating the design and implementation of the data models, a number of the views, and creating the main logo for the home page in Photoshop. I also undertook a good proportion of the work needed to keep our Trello board updated.

### Project Aims
- Build a more complex application in a team setting, creating our own API and using AngularJS for the front-end
- Provide users with the ability to annotate one, or more, of their books with a code randomly generated on our app, and to detail where the book was left, along with their own thoughts on it.
- For someone finding the book, the app had to be capable of retrieving the book by the random code and giving its finder the ability to record where they'd found it, along with their own comments.

![Free-the-Books landing page](../project_03_01.png)
Our apps landing page

### Technologies Used
- HTML
- CSS/SASS
- Skeleton
- AngularJS
- Express.js
- MongoDB API
- Mongoose
- Google Maps
- JWT token authentication
- Slick
- Shortid
- Gulp
- Babel

![An initial design concept for the Free the Books app](../project_03_05.jpg)
An early storyboard idea

### Successes
- With this project, we had a number of occasions where 'bug fixing' was a very strong suit for our team; most notably with Slick and our Google API keys
- Working with the Google Books API, and building a method for sharing multiple API keys and also reduce the number of calls to the API
- Development of an overall 'look & feel' for the site, and following this through to implementation
- Resolution of conflict situations in a team setting


### Challenges
- The Slick carousel package caused a major site outage, as it impacted on the Angular version in use
- Challenges in coordinating GIT push/merge tasks
- Initial plan was iterated on in ad-hoc fashion
- We didn’t always work as a team


![The team Trello Board used to plan the Free the Books app](../project_03_01_trello.png)
An active Trello board

### Future Development
- Inclusion of top users and most ‘freed’ books
- Links to social media
- Addition of Google Directions
- More work needed on ensuring the site is mobile friendly
- Printable labels inserting into the books on release


### Live Version
- a live version of the app can be found on Heroku at ['Photo Walk'](https://fierce-fortress-98221.herokuapp.com/)
- The code for the app can be located on ['GitHub' - 'WDI_PROJECT_3'](https://github.com/christopherallanperry/WDI_PROJECT_3)
- To get started, register on the site as a new user

![The Free the Books book feed](../project_03_03.png)