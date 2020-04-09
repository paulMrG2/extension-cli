<img src="https://raw.githubusercontent.com/MobileFirstLLC/extension-cli/master/guide/assets/images/favicon.png" width="64" alt="Extension CLI">  

# Extension CLI

[![npm](https://img.shields.io/npm/v/extension-cli)](https://www.npmjs.com/package/extension-cli)
[![travis](https://img.shields.io/travis/mobilefirstllc/extension-cli)](https://travis-ci.org/MobileFirstLLC/extension-cli)
![david](https://img.shields.io/david/mobilefirstllc/extension-cli)
[![Maintainability](https://api.codeclimate.com/v1/badges/abbf1b25f926d75bb9df/maintainability)](https://codeclimate.com/github/MobileFirstLLC/extension-cli/maintainability)

* * *

**This application includes command-line build tools that facilitate rapid chrome extension development by providing
systematic way to build, test and document extension projects.**

* * *

## Features

*  **Javascript Bundling** — Compiles and bundles javascript files (including [ES6 syntax](http://es6-features.org/) w/ babel and webpack)                                                                                                           

*  **CSS Bundling** — Compiles, bundles, and minifies CSS and [SASS files](https://sass-lang.com/guide)                                                                                                                                                          

*  **Linting** — Code linting using [ESLint](https://eslint.org/)                                                                                                                                                                        

*  **.zip Generation** — Generates a `.zip` file for uploading to [Chrome Web Store](https://chrome.google.com/webstore/category/extensions)                                                                                         

*  **Source Code Docs** — Generates code documentation using [JSDoc](https://jsdoc.app/about-getting-started.html)                                                                                                                                

*  **Unit Testing** —  Sets up a unit testing environment with [mocha](https://mochajs.org), [chai](https://www.chaijs.com/), [sinon-chrome](https://github.com/acvetkov/sinon-chrome), and [js-dom](https://github.com/rstacruz/jsdom-global) 


## Motivation

After developing multiple browser extension, it became clear that there were several steps in the development process that stayed the same between every project. 

Instead of setting up these tasks individually for each project, it made more sense to wrap everything in a utility tool that could be shared between projects. 

This approach helps with creating a common, consistent development approach between multiple projects, reduces time to get started, and makes it easier to update build tools and scripts across multiple projects as many npm packages inevitably need to be updated (frequently!).

**Author:** [Mobile First](https://mobilefirst.me)

**License:** [MIT](https://github.com/MobileFirstLLC/extension-cli/blob/master/LICENSE)

**Issues and Feature Requests:** [Submit on Github](https://github.com/MobileFirstLLC/extension-cli/issues/new/choose)


## Getting Started & Docs

**Docs: [View Full Guide](https://oss.mobilefirst.me/extension-cli)**

Basic install:

    npm install extension-cli

## Commands

<!-- Generated by documentation.js. Update this documentation by updating the source code. -->

### xt-build

Build command generates a dist/ directory that can be
debugged in the browser. When called with production env flag, `-e prod`,
this command will minify and compile a `release.zip` file that can be
uploaded to Chrome Web Store for distribution.

### xt-clean

Clean operation iterates over files and directories listed in the
project `.gitignore` file, and removes all ignored files and
directories, except `node_modules`, `.idea/`, and `.vscode`. To remove these
directories, you must explicitly pass a flag to delete each one of them.

### xt-create

Once implemented, this command can be used to create a new extension project.

### xt-docs

Docs command generates documentation for the project. This command uses
jsdocs syntax. See [About JSDoc](https://jsdoc.app/index.html) for more details,
including [configuration options here](https://jsdoc.app/about-configuring-jsdoc.html).

The default template for the docs is [FooDoc](https://github.com/steveush/foodoc#readme).
You can override this theme in the project by changing `opts.template` in jsdoc config file.

By default, this command will automatically look for configuration in the project `package.json`.
Use `"xtdocs"` key to define config options in `package.json`. Alternatively add a separate
configuration file `.xtdocs.json` in the project root; or explicitly provide a path to a config file.
If you want to define configuration in some other location, use -c/--config flag
to provide path and name of the configuration file.

### xt-sync

The purpose of this command is to upgrade configuration files of
a stale project to latest version, where this CLI tool will provide
updated project configuration files. If the config files have been
modified heavily for the project, it is not advisable to upgrade them
in this manner. Instead you should upgrade such configs manually.

### xt-test

This command will run project unit tests located in test/ directory.

This command will setup extension testing environment that is pre-initialized
with [mocha](https://mochajs.org/), [chai](https://www.chaijs.com/) (including chai-as-promised)
and expect. [nyc](https://www.npmjs.com/package/nyc) is used for computing code coverage.
The following browser APIs are also initialized: `window`, `chrome`. Window
is setup using [jsdom-global](https://www.npmjs.com/package/jsdom-global) and
chrome using [sinon-chrome](https://www.npmjs.com/package/sinon-chrome).

Mocha will execute with babel, meaning you can use this test environment to
test ES6 modules with imports, arrows, and classes.

You may extend this test environment with a single project; this is simply the base setup
for running unit tests. Or you may create your own test environment if this is not suitable.

---

<p align="center">
<strong><a href='https://oss.mobilefirst.me/extension-cli/'>View Complete User Guide &rarr;</a></strong>
</p>

---
