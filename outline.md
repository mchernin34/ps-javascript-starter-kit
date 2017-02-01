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
