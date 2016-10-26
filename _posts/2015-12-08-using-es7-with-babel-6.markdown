---
title:  "Running ES7 with Babel 6"
date:   2015-12-08 10:18:00
description: Babel 6 setup to run ES7 on demand
---

[TL;DR](#tldr). Babel is the one of my favourite Node.js module. It enables us to use the next generation javascript today. But last 5-6 months or 1 year, I don't remember, I haven't used it in any project and now I see there are lots of changes.

The biggest thing I see is that every piece of Babel consists of plugins so that you are able to use what you need. For example, you only want to use ES6 classes then you only need to use ```babel-plugin-transform-es2015-classes``` module.

Anyway, I'm a bit lazy and want to include all plugins and use them in my personal project. Fortunately, the babel contributors thought something like named **presets**.

> A preset includes couple of plugins.

There are a few standard presets for different needs. (React, ES6, ES7 etc.)

In the past, this code would be enough for me to use ES7: ~~```require('babel/register')({ stage: 0 });```~~

The time changes everything. Lets go with the simplest configuration.

### Require Hook
Assume that we have ```app.js``` file and it starts all the application codes. Before running app.js we need to load Babel. It will make some changes in node require hook to compile scripts on the fly. Unfortunately, we are not able to load Babel and run ES7 code in the same file.

We need to create another file like named ```boot.js```. It should be something like this:
```language-javascript
...babel loader code here...
require('./app.js');
```

### Installation
First we need to install babel-register plugin. This will override require hook.
```
npm install babel-register --save
```

Then install ES2015 preset. This includes all ES6 plugins.
```
npm install babel-preset-es2015 --save
```

And of course we should install all ES7 plugins.
```
npm install babel-preset-stage-0 --save
```

The last module is babel-polyfill. It adds some missing  ES6 runtime functions.

```
npm install babel-polyfill --save
```

### Importing Babel
Now, we are going to prepare the lastest version of our boot.js file. Import babel-register with the given presets and babel-polyfill.

```language-javascript
require('babel-register')({ presets: ['es2015', 'stage-0'] });
require('babel-polyfill');
require('./app.js');
```

Then run the application
```
node boot.js
```

I test whether it runs by creating ```app.js``` file including this code:
```language-javascript
class A { async run() {} }
```

If it works everything seems perfect.

By the way, this is my first article in this blog and the second one in english. If you have any feedback or see any wrong please let me know. Thanks for reading.

### TL;DR
```
npm install babel-register --save
npm install babel-preset-es2015 --save
npm install babel-preset-stage-0 --save
npm install babel-polyfill --save  
```

```language-javascript
require('babel-register')({ presets: ['es2015', 'stage-0'] });
require('babel-polyfill');
require('./app.js');
```

##### See also
- [Babel](http://babeljs.io)
- [Babel Plugin List](http://babeljs.io/docs/plugins/)
