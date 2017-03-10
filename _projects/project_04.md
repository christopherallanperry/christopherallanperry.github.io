---
layout: project
title: Our Survey Said...
subtitle: A project to provide a tool that can be used to capture customer or employee feedback, through a set of structured question types.
heroku: https://chris-perry-wdi-project-4.herokuapp.com/
github_client: https://github.com/christopherallanperry/wdi_project_4-client
github_api: https://github.com/christopherallanperry/wdi_project_4-api
repo_name_client: wdi_project_4-client
repo_name_api: wdi_project_4-api
---

As a long time photographer and participant in photo walks with friends, I wanted to try my

<h3>Try the project on Heroku: <a href="{{ page.heroku }}">{{ page.title }}</a></h3>
<h3>View the client code on GitHub: <a href="{{ page.github_client }}">{{ page.repo_name_client }}</a></h3>
<h3>View the API code on GitHub: <a href="{{ page.github_api }}">{{ page.repo_name_api }}</a></h3>

## Aims
- Build an application that would leverage the Google Maps API
- Provide the ability for users to create their own walk by either selecting existing landmarks, or by adding landmarks of their own
- Give the user the ability to record their walks and show the images they took during it

## Technologies Used
- HTML
- CSS/SASS
- Skeleton
- AngularJS
- Express.js
- MongoDB API
- Mongoose
- Google Maps
- JWT token authentication
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
- a live version of the app can be found on Heroku at ['Photo Walk'](https://fierce-fortress-98221.herokuapp.com/)
- The code for the app can be located on ['GitHub' - 'WDI_PROJECT_4'](https://github.com/christopherallanperry/WDI_PROJECT_3)
- To get started, register on the site as a new user

![IMAGE]()
