---
layout: project
title: Minesweeper
subtitle: A Recreation of Microsoft's Classic Desktop Game
<!-- image: ../project_01_winning_game.png -->
heroku: https://frozen-eyrie-56010.herokuapp.com/
github: https://github.com/christopherallanperry/WDI_PROJECT_1
repo_name: WDI_PROJECT_1
---

As my first project for the Web Development Immersive course (WDI_24) at General Assembly London, I chose to recreate the classic Microsoft Minesweeper game, as I felt it represented an interesting range of challenges around the logic needed to implement the game play.

<h3>Try the project on Heroku: <a href="{{ page.heroku }}">{{ page.title }}</a></h3>
<h3>View the code on GitHub: <a href="{{ page.github }}">{{ page.repo_name }}</a></h3>

## Aims
- Complete a re-creation of the ‘Minesweeper’ game found on MS Windows operating systems
- Ensure it would play on modern browsers using a mouse with left/right buttons
- Style it to replicate the ‘classic’ game look and feel

## Technologies Used
- HTML
- CSS
- JavaScript (inc. some ES6)

![Winning Game](../project_01_game_in_play.png)

## Successes
- The game was written in ‘vanilla’ JS with no use of jQuery or 3rd Party libraries
- Grasping the core concept of how the game logic worked and planning the pseudo code around that
- Extending practical working knowledge of functions and how they behave
- The styling worked out well

## Challenges
- Accessing variable values in the form required
- Learning how a recursive function has to be structured
- Early use of jQuery was refactored out as it was blocking progress
- Keeping the code ‘DRY’

![Winning Game](../project_01_losing_game.png)

## Future Development
- Extend use of OOP
- Reduce the size of the codebase
- Add other grid size options (9x9, 30x16)
- Make the game playable on a touchscreen or mobile devices
- Convert to a Progressive Web App (PWA)

## Live Game Version
- a live version of the game can be found and played on Heroku at ['Minesweeper'](https://frozen-eyrie-56010.herokuapp.com/)
- The code for the game can be located on ['GitHub' - 'WDI_PROJECT_1'](https://github.com/christopherallanperry/WDI_PROJECT_1)
- To get started, click on a random tile to reveal what it covers, or right-click to flag a square as being suspected of covering a mine.

![Winning Game](../project_01_winning_game.png)
