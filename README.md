# Integrate Travis CI into you Yeoman project [![Build Status](https://secure.travis-ci.org/manuelvanrijn/yeoman-travis-ci.png)](http://travis-ci.org/manuelvanrijn/yeoman-travis-ci)

This is an example project that show's how you can integrate your [Yeoman](http://yeoman.io/) project into [Travis CI](http://travis-ci.org). With just a few lines you'll be able to automatically test your Yeoman project whenever you push something to GitHub.

## Prerequisites

The add support for Travis CI you should have Yeoman installed and have a initialized project. See the [yeoman.io](http://yeoman.io/) website for more information on this.

## Adding Travis CI support

### TL;DR;

See [this commit](https://github.com/manuelvanrijn/yeoman-travis-ci/commit/32203d84ca2dbba2faa671e55afede8a1e6666df) with all the changes you have to make.

### package.json

First you have to add `yeoman` as a dependency to your `package.json` file:

```yml
"devDependencies": {
  "yeoman": "~0.9.1"
}
```

Now run `npm install` to install the packages in your `node_modules` folder within your project.

Second, you have to make the `npm test` command aware it should execute `yeoman test` by adding these lines:

```yml
"scripts": {
  "test": "node_modules/.bin/yeoman test --verbose"
}
```

Now you can test the command by running `npm test`

### Add some tests

At this point you can add some test into your project.

### Add the .travis.yml

Create a `.travis.yml` file in the root of your project with the following content:

```yml
language: node_js
node_js:
  - 0.8
  - 0.9
```

## Hook & Push!

At this point you only have to add the Travis CI hook to you project in GitHub and push your project.

[![githalytics.com alpha](https://cruel-carlota.pagodabox.com/7cca718214448b438fe9d223263a56e2 "githalytics.com")](http://githalytics.com/manuelvanrijn/yeoman-travis-ci)
