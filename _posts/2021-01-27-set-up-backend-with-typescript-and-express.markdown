---
layout: post
title: 'Set Up a Backend Server with Typescript and Express'
date: 2021-01-27 12:58:31 -0800
categories: jekyll update
---

1. Run `npm init` to create your package json for the project

2. Run `yarn add -D typescript nodemon @types/node` this will add dev dependencies allowing us to use typescript, the node types, and nodemon to rerun the application on every file update.

3. Run `npx tsconfig.json` to create a config file for typescript. This file sets settings for using typescript.

4. Create a `src/index.ts` file from the root. In this file add `console.log('hello world')`

5. Create scripts in the package json
   {% highlight ruby %}
   "scripts": {
   "watch": "tsc -w",
   "start": "node dist/index.js",
   "dev": "nodemon dist/index.js",
   },
   {% endhighlight %}

   - `watch` will convert all the typescript code into javascript and place it in the `dist` folder in the root. The `-W` is watch meaning the command will watch for changes in the typescript files and rebuild the dist folder when those files are changed.
   - `start` will target the dist/index.js file and run the file using node.
   - `dev` will run dist/index.js with nodemone which means it will listen for changes in the dist folder and rebuild the application.
