# mean-stack-dev

My Notes for MEAN Stack Development

## Node.js

### installation

I always install the stable LTS version of node.js via system installer from [nodejs.org](https://nodejs.org/en/).

Additionally I install [NVM (node version manager)](https://github.com/creationix/nvm) to switch easily between different version of node.js and npm.

I am using nvm with aliases v4 (v4.x.x, currently: v4.3.0) and v5 (v5.x.x, currenly: v5.6.0)

## MongoDB

because of major changes in mongodb v3.2 ensure that you use the latest v.3.2.x version of mongodb. Especially for usage of wiredTiger storageEngine and for changes in aggregration pipeline framework.

If you are new to mongodb, I can recommend the mongodb university. In my case I did the [M101JS: MongoDB for Node.js Developers](https://university.mongodb.com/courses/M101JS/about) online course. A very good way to get familiar with MongoDB.

### Documentation

I have struggled many times that I have opened the wrong MongoDB Documentation or the old MongoDB Node.js Driver Documentation.

Now I have bookmarks in my browser:

- [MongoDB v3.2 Manual Reference](https://docs.mongodb.org/manual/reference/)
- [MongoDB Node.js 2.0 Driver API](http://mongodb.github.io/node-mongodb-native/2.0/api/Cursor.html)
- [Mongo Shell Doc](https://docs.mongodb.org/manual/tutorial/write-scripts-for-the-mongo-shell/)

## Global NPM Modules

- yo
- grunt-cli
- gulp
- bower
- mocha
- istanbul

```npm install -g yo grunt-cli gulp bower mocha istanbul```

## Generators

to get a good starting point for my projects I use the angular-fullstack yeoman generator.

```npm install -g generator-angular-fullstack```
  
**But I am not yet comfortable with the latest changes, adopting the ES6 things and therefore using the babel transpiler. For that reason I have also installed and linked a version of angular-fullstack at version 2.1.1**

To have both generators available as commands. I clone the repo at v2.1.1 tag, rename the module in package.json to "generator-angular-fullstack2" and link that module now to be available in my global installed modules.

```
  mkdir angular-fullstack2
  sed 's/generator-angular-fullstack/generator-angular-fullstack2/g' package.json > package.json.n
  rm package.json && mv package.json.n package.json
  npm install
  npm link
```
  
After that I can both use 

```
  #latest
  yo angular-fullstack 
  #and v2.1.1
  yo angular-fullstack2
```

I have started a fork of angular-fullstack based on branch `legacy-2.x.x` to fix issues. e.g. npm install failed last time when creating a new project and going to run npm install because of incompatible version of grunt-node-inspector. (I have just updated the version in package.json)

- [SBejga/generator-angular-fullstack2](https://github.com/SBejga/generator-angular-fullstack2)
 
```
git clone https://github.com/SBejga/generator-angular-fullstack2
cd generator-angular-fullstack2
git checkout legacy-2.x.x
npm install 
npm link
```

### server-side only geneator (MEN Stack)

  There is a server-side only from angular-fullstack generator (also from my prefered v2.1.1) called [generator-node-express-mongo](https://github.com/Liam-Williams/generator-node-express-mongo)
  
    npm install -g generator-node-express-mongo
    
