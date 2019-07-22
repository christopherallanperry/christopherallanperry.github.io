---
layout: post
title:  "MongoDB Upgrade Error"
date:   2019-07-22 22:30:00 +0000
categories: blog
---
## MongoDB Upgrade Error

If you should ever encounter an error message along the lines of the following, go to the StackOverflow link lower down and follow the instructions carefully - it works!

My best guess is that the problem was caused by running `$ brew update` followed by `$ brew upgrade` giving a version conflict somewhere along the line.

<blockquote>** IMPORTANT: UPGRADE PROBLEM: The data files need to be fully upgraded to version 3.6 before attempting an upgrade to 4.0; see [http://dochub.mongodb.org/core/4.0-upgrade-fcv](http://dochub.mongodb.org/core/4.0-upgrade-fcv) for more details.</blockquote>

[https://stackoverflow.com/questions/51227939/using-brew-upgrade-mongo-update-from-3-4-to-4-0-error-the-data-files-need-to-be](https://stackoverflow.com/questions/51227939/using-brew-upgrade-mongo-update-from-3-4-to-4-0-error-the-data-files-need-to-be)