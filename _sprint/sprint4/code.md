---
layout: page
title: Executable Code and Instructions
---

## Desktop Application

You can find the latest executables [here](https://github.com/360ls/desktop/releases).

### Windows
1. Download the Windows release.
2. Unzip the file and open the executable inside.


### Ubuntu/Debian
1. Download the debian release.
2. Run `sudo dpkg -i 360ls-Desktop-Application-1.0.0-amd64.deb`.

### MacOS
1. Download the MacOS release.
2. Unzip the file and open the executable inside.


## Stitcher Application

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

## Developing and Building the Desktop Application

You can find the instructions for setting up a developer
environment for the desktop application [here](https://github.com/360ls/desktop/blob/master/README.md).
