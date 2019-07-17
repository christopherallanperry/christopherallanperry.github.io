---
layout: post
title:  "MEAN Stack: Building a VueJS Front-End onto a NodeJS API - Part 2"
date:   2018-02-12 20:00:00 +0000
categories: blog
---
## Background
In the first part of this article...

## GitHub Repo
You can find the code for this series on my [GitHub repo 'YATA'](https://github.com/christopherallanperry/yata). The article describes the application it sets out to create as an 'Awesome Bucket List Application', but we all know it's a TODO list, hence the repo name YATA (Yet Another Todo App). As a quick PSA, be aware that the repo is still undergoing further development as I learn more and find other things to tweak.

## Getting Setup to Use VueJS
```cli
$ npm install -g vue-cli
$ vue init webpack vue_src
$ cd vue_src
$ npm install
$ npm run dev
```
[CLI article](https://medium.com/codingthesmartway-com-blog/vue-js-2-quickstart-tutorial-2017-246195cfbdd2)

## Renaming HelloWorld
We'll be working for the most part in the `vue_src/src/` folder, so unless otherwise mentioned, the changes we're going to make will be be in files or sub-directories below that.

First, let's rename the `components/HelloWorld.vue` file to `components/ViewList.js`, and then make a few alterations to take account of that name change.

In the `components/ViewList.js` file, change the value for the `name:` key to `ViewList`. The script section should now contain...

```js
export default {
  name: 'ViewList', // <-- only change the value in this key/value pair
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
```

In the `router/index.js` file, again replace `HelloWorld` with `ViewList` so that the file contains...

```js
import Vue from 'vue';
import Router from 'vue-router';
import ViewList from '@/components/ViewList';

Vue.use(Router);

export default new Router({
  routes: [
    {
      path: '/',
      name: 'ViewList',
      component: ViewList,
    },
  ],
});
```
On saving these files, you should see the project re-build and if you now look at the boilerplate VueJS website, you should see no change. This is OK, as we've not changed any of the visible content yet, and we've not broken anything. Our next step is to find the data in the API we built in Part 1....

## Locating the API data
VueJS doesn't come with a built-in method for accessing data and it's don't specifically recommend one. For our purposes here, I've chosen to use the popular [axios](https://github.com/axios/axios) library. To include axios in your project, execute the following:

```cli
$ npm install axios --save
```
With that done, we can now focus on connecting to our bucketlist API - `http://localhost:3000/bucketlist`. For this, the `script></script>` section in needs to be expanded out like so...

```js
import axios from "axios";

    export default {
        name: 'ViewList',
        data () {
            return {
                items: ""
            }
        },
        mounted() {
          axios({ method: "GET", "url": "http://localhost:3000/bucketlist" }).then(result => {
                this.items = result.data.lists;
                console.log(result.data.lists);
            }, error => {
                console.error(error);
            });
        },
        methods: {
          // we'll look at these shortly
        }
    }
</script>
```
Here you can see that we've added a `mounted()` function to the `name:` key/value pair, and also an empty `methods:` key, to the object we're exporting.

## References
[Consume Remote API Data Via HTTP In A Vue.js Web Application](https://www.thepolyglotdeveloper.com/2017/10/consume-api-data-http-vuejs-web-application/)
[CLI article](https://medium.com/codingthesmartway-com-blog/vue-js-2-quickstart-tutorial-2017-246195cfbdd2)
<br>
<br>
