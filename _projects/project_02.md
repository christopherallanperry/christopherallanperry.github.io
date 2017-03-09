---
layout: project
title: Photo Walk
subtitle: A project designed to give photographers a guided tour of local photo opportunities
<!-- image: ../project_01_winning_game.png -->
heroku: https://photo-walk.herokuapp.com/
github: https://github.com/christopherallanperry/WDI_PROJECT_2
repo_name: WDI_PROJECT_2
---

As a long time photographer and participant in photo walks with friends, I wanted to try my hand at an application that could combine the Google Map API with the idea of marking specific known photo opportunities. The idea crystallised when I was given a gift of the book ["Whitechapel in 50 Buildings"](https://www.amberley-books.com/whitechapel-in-50-buildings.html) by [Louis Berk](http://www.louisberk.com/) and [Rachel Kolsky](http://www.golondontours.com/about-me-2/) for Christmas. This provided me with a ready source of locations nearby where [General Assembly](https://generalassemb.ly/locations/london) were operating from.

<h3>Try the project on Heroku: <a href="{{ page.heroku }}">{{ page.title }}</a></h3>
<h3>View the code on GitHub: <a href="{{ page.github }}">{{ page.repo_name }}</a></h3>

## Aims
- Build an application that would leverage the Google Maps API
- Provide the ability for users to create their own walk by either selecting existing landmarks, or by adding landmarks of their own
- Give the user the ability to record their walks and show the images they took during it

## Technologies Used
- HTML
- CSS
- JavaScript (inc. some ES6)
- Express.js framework
- MongoDB API
- Google Maps
- JWT token authentication
- SASS
- Pure.css
- Gulp
- Babel

![IMAGE]()

## Successes
- Building an API to house the locations to be placed on the map, and getting this seeded with suitable data
- Creating a re-useable (DRY) function for creating a modal where required
- Learning how the Google Maps API works, and seeing the extent to which it can be manipulated


## Challenges
- Working with a single `client.js` file that contained API, map, template and application logic
- Developing a good understanding of MVC build patterns and the way which they are structured
- Time constraints involved in creating a minimum viable product


![IMAGE]()

## Future Development
- Add the ability to upload images
- Enhance the 'admin' functionality and backend management tools


## Live Version
- a live version of the app can be found on Heroku at ['Photo Walk'](https://photo-walk.herokuapp.com/)
- The code for the game can be located on ['GitHub' - 'WDI_PROJECT_2'](https://github.com/christopherallanperry/WDI_PROJECT_2)
- To get started, register on the site as a new user

![IMAGE]()
