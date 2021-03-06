## Outline

### Code Editor

#### Features to look for

- Strong ES2015 support
- Framework intelligence
- Built in terminal

#### JavaScript Editors

- WebStrom
  - IDE
- Atom
- Sublime Text
- Brackets
  - Great built in features, like live-reload
- VSCode
  - Code intelligence
  - Strong Git integration

#### EditorConfig

One set of configuration settings that works in all editors and that can be committed to the project repository. This way all team members get a consistent editor environment.

### Package Manager

#### Installing Node and NPM

1. Go to [Node's website](https://nodejs.org) and download and install the latest version of Node.
2. Install basic and essential NPM packages from [the gist](http://bit.ly/jsdevpackagejson). You should copy the file to a package.json file in the project directory.
3. In the terminal type `$ yarn` to install the packages.

#### Security Check

We should run a security check in order to find malicious packages.

##### When to Run Security Check

- Manually - easy to forget.
- `$ npm install` - may have issues later.
- Production build - expensive to change.
- pull request - expensive to change.
- `$ npm start` - slows start slightly

The best method for a security check is during `$ npm start`, although it is slightly slower than other methods and also requires an internet connection.

##### Running a Security Check

1. `$ yarn global add nsp`
2. `$ nsp check`

### Web Server

##### live-server

- Lightweight
- Supports live-reloading

##### Express

- Comprehensive
- Highly configurable
- Production grade
- Can run it everywhere

##### Webpack Dev Server

- Built into Webpack
- Serves from memory
- Includes hot reloading

##### BrowserSync

- Dedicated IP for sharing work on LAN
- All interactions remain in sync
- Great for cross device testing
- Integrates with Webpack and Express

### Sharing Work in Progress

#### localtunnel

Easily share work on your local machine.

Setup:
  1. `$ npm i -g localtunnel`
  2. Start your app
  3. `$ lt --port 3000`

#### ngrok

Secure tunnel to your local machine.

Setup:
  1. Sign up
  2. Install ngrok
  3. Install authtoken
  4. Start your app
  5. `$ ./ngrok http 80`

#### now

Quickly deploy Node.js to the cloud.

Setup:
1. `$ npm i -g now`
2. Create start script
3. `$ now`

#### Surge

Quickly host static files to public URL.

Setup:
1. `$ npm i -g surge`
2. `$ surge`

### Automation

#### Grunt

- The "original"
- Configuration over code
- Writes intermediary files between steps
- Large plugin ecosystem

#### Gulp

- In-memory streams - faster than Grunt
- Code over configuration
- Large plugin ecosystem

#### NPM Scripts

- Declared in package.json
- Leverage your OS' command line
- Directly use npm packages
- Call separate Node scripts
- Convention based pre/post hooks
- Leverage world's largest package manager

Advantages over Gulp and Grunt:

- Use the tool directly, without any plugins
- Simpler debugging
- Better docs
- Easy to learn
- Simple

##### Notes

- Add your scripts under `"scripts": { ... }` in package.json.
- `prestart` and `poststart`: Scripts that run before and after the main ones.
- `start`: Main script, doesn't require the `run` keyword.
- `npm-run-all --parallel script1 script2`: Execute multiple scripts at once.

##### Basic Scripts

- `node pathToServer/server.js` - Start basic node server.
- `nsp check` - Check packages in package.json for malicious code.
- `lt --port 3000` - Start a secure cloud server in port 3000.

### Transpilers

#### TypeScript

- Superset of JS
- Enhanced autocompletion
- Safer refactoring
- Clearer intent

#### Elm

- Compiles down to JS
- Clean syntax
- Immutable data structures
- Friendly errors
- All errors are compile-time errors
- Interops with JS

#### Babel

Allows for modern, standards-based JavaScript, today.

##### Adding Babel

Add `babel-` before the `node` command in the scripts section of package.json.

##### Converting CommonJS to ES6 Modules

Before: `var express = require('express');`

After: `import express from 'express;'`

### Bundlers

#### Why Bundle?

- CommonJS doesn't work in we browsers
- Package project into file(s)
- Improve Node performance

#### Browserify

- The first bundler to reach mass adoption
- Bundle npm packages for the web
- Large plugin ecosystem

#### Rollup

- Tree shaking
- Faster loading production code
- Newest
- Great for library authors
- No hot reloading and code splitting yet

#### JSPM

- Uses SystemJS, a universal module loader
- Can load modules at runtime
- Has its own package manager
- Can install from npm or Git
- Uses Rollup

#### Webpack

- Bundles more than just JS
- Import CSS, images, etc like JS
- Bundle splitting
- Built in hot reloading web server, no need to fill the whole form while testing
- Tree shaking in Webpack 2

### Linters

With a linter you can enforce consistency while avoiding mistakes.

#### Configuring ESLint

- Configuration file format
- Linting rules
- Warnings or errors?
- Plugins
- Just use a preset?

##### Tip:

Add `/* eslint-disable [rule] */` or `/* eslint-disable-line [rule] */` to disable ESLint for that rule.

### Testing and Continous Integration

1. Framework - Mocha
2. Assertion Library - Chai
3. Helper Libraries - JSDOM
4. Where to run tests - Node
5. Where to place test - Alongside code
6. When to run tests - Upon save

#### Travis CI

- Cloud based
- Built on linux
- Free for open source projects

#### Appveyor

- Cloud based
- Built on Windows
- Free for open source projects

#### Jenkins

- Free hosted edition
- Can be hosted on every platform

### Mocking HTTP Calls

#### Planning

1. Declare our schema
  - JSON Schema Faker
2. Generate random data
  - faker.js
  - chance.js
  - randexp.js
3. Serve data via API
  - JSON Server

### Error Login

#### What to look for

- Error metadata
  - Browser
  - Stack trace
  - Previous actions
  - Custom API for enhanced tracking
- Notifications & integrations
- Analytics and filtering
- Pricing

### Seperating UI from API

#### Why should we seperate?

- Simple, low-risk, UI only deploys
- Seperates concerns
  - Seperate teams
  - Less to understand
  - Scale back-end seperately
- Cheap UI hosting - static files
- Serve UI via a CDN
- Use the API tech you like

#### Setting up cloud API hosting on Heroku

1. Go to [Heroku](https://heroku.com) and sign up for a free account.
2. Go to the Node docs and download and install the Heroku CLI.
3. Navigate to your API repository.
4. In terminal:
  - `$ heroku` - Check that Heroku CLI is installed.
  - `$ heroku create` - Create an Heroku app and get a URL.
  - `$ heroku git:remote -a [Heroku app name]` - Attach a remote to your API repository.
  - `$ git push heroku master` - Push the repository to Heroku.
5. Go to *https://[Heroku app name].herokuapp.com* and check that the API is in place.
