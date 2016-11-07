---
layout: page
title: Executable Code and Instructions
---

## For the most up-to-date stitching functionality:

### Install OpenCV
360ls-stitcher requires `OpenCV` to be installed. 
Listed below are instructions for installing OpenCV
for various platforms.
- [Linux](http://docs.opencv.org/2.4/doc/tutorials/introduction/linux_install/linux_install.html)
- [Windows](http://docs.opencv.org/2.4/doc/tutorials/introduction/windows_install/windows_install.html)
- [OSX](http://www.mobileway.net/2015/02/14/install-opencv-for-python-on-mac-os-x/)

### Install Python
Python 2.7 is required for running 360ls-stitcher.
You can get find the release for a specific platform [here](https://www.python.org/downloads/release/python-2712/).

### Clone the stitch-flex repository

```bash
git clone https://github.com/360ls/stitch-flex.git
```


### To install the package:

```bash
cd stitch-flex
git checkout origin checkpoint/sprint3
make clean-install
```

This will install package dependencies via npm (node.js) and pip (python), including the yarn package manager dependency.

### Then, to run the app, either:

```bash
make run
```
to simply run the app

OR

```bash
make
```

to clean the package, do a fresh (but not brand new) install of dependencies, and then run the app.

### To run the cli, which provides the most functionality.:
```bash
make cli
```

### To set up the camera streams
```bash
make camera-setup
```

### To demonstrate threading through taking snapshots
```bash
make snap
```

### To lint the application:

For JS files:
```bash
eslint nameoffile.js
```

For Python files;
```bash
make lint-py
```

### To run tests against the application:

```bash
make test
```

-------

## For the most up-to-date desktop interface functionality:

For package management, we use the [Yarn](https://yarnpkg.com/) package manger.

### To Install Yarn and Install dependencies:

```bash
npm install -g yarn
yarn install
```

### To run the application:

```bash
yarn run dev
```

This will start up the build server that bundles the application
with [webpack](https://webpack.github.io/) and open up the
electron application.


### Linting

[ESlint](http://eslint.org/) is used to lint `js`/`jsx` files under the
`app` and `test` directories using the `React` style guide from
[Airbnb](https://github.com/airbnb/javascript/blob/master/react/README.md).

To lint run the following command:

```bash
yarn lint
```

## Testing

Tests are run using the [Jest](https://facebook.github.io/jest/) framework.
The following command will run the test suite defined under the `test`
directory.

```bash
yarn test
```
