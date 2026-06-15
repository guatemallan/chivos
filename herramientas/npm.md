

# NPM + command line

## NPM, Node Package Manager

    "Imagine building your own CSS framework: You’d be creating your own design systems, utility classes, different colors and their shades, thousands of lines of Sass (which will eventually be compiled to CSS), numerous custom components, tests for bugs, and financing (if other developers are helping you build such a project). This can be tedious — and expensive — work."

NPM is a JavaScript online repository for open-source Node.js packages. It's owned by Github, which is owned by Microsof.

## Node.js

Node.js is a cross-platform, open-source JavaScript runtime environment that can run on Windows, Linux, Unix, macOS, and more. Node.js runs on the V8 JavaScript engine, and executes JavaScript code outside a web browser.

## Why Use npm?

- It enables you to install libraries, frameworks, and other development tools for your project, similar to installing a mobile application from an app store.
- You gain access to safe Node.js projects for development.
- It helps you speed up the development phase by using prebuilt dependencies.
- npm has a wide variety of tools to choose from for no cost.
- Using npm commands doesn’t require a lot of learning, as they’re easy to understand and make use of.

## NPM Commands

// LOCAL OR GLOBAL
// The DEFAULT is LOCAL, 
//      which means it will perform the action at the local directory
// For Global 
//      add the flag -g, which make the action to be applied 
//      to all directories (whole computer)
`
// INSTALL, installs a package
npm i <PackageName>
npm install <PackageName>

// UNISTALL, uninstalls a package
npm uninstall <PackageName>

// UPDATE, updates an already installed packate
npm update                          # updates all
npm update <PackageName>            # updates specific package
npm install npm@latest -g           # updates npm and it's packages to the latest

// START, start a package
npm start [ <PackageName> ]

// STOP, stop a package from running
npm stop c

// RESTART, stop and then start
npm restart [ <PackageName> ]

// VERSION
npm -v                              # displays npm version
nmp version                         # displays the version of all packages
node -v                             # displays node version

// Who Am I?, displays npm username
nmp whoami

// INIT, initialize a new projct, creates the package.json file
npm init                            # you will be prompted for details
npm init -y                         # use default configuration

// DOCUMENTATION
npm [ <command> ] -h
npm help [ <topic> ]
npm docs [ <topic> ]

// LIST installed packates
npm list [-g]

### Sources
https://kinsta.com/knowledgebase/what-is-npm/
https://www.npmjs.com/
https://docs.npmjs.com/cli/v10/commands