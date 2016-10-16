---
layout: page
title: Executable Code and Instructions
---
## Install OpenCV
360ls-stitcher requires `OpenCV` to be installed. 
Listed below are instructions for installing OpenCV
for various platforms.
- [Linux](http://docs.opencv.org/2.4/doc/tutorials/introduction/linux_install/linux_install.html)
- [Windows](http://docs.opencv.org/2.4/doc/tutorials/introduction/windows_install/windows_install.html)
- [OSX](http://www.mobileway.net/2015/02/14/install-opencv-for-python-on-mac-os-x/)

## Install Python
Python 2.7 is required for running 360ls-stitcher.
You can get find the release for a specific platform [here](https://www.python.org/downloads/release/python-2712/).

## Install 360ls-stitcher
First clone the 360ls-stitcher repo and checkout the results/sprint1 branch.

```bash
git clone https://github.com/dongy7/360ls-stitcher.git
git checkout origin/results/sprint1
```

Install the dependencies:

```bash
make install
```

## Generating a user profile
360ls-stitcher requires a configuration file called a profile. In order to create one,
run the following command:

```bash
make configure
```

Follow the instructions and fill in the requested information. The
resulting profile will be stored as a *YML* file at `config/profile.yml`.

## Starting 360ls-stitcher
After a profile has been generated, run the following command to start 360ls-stitcher:

```
make run
```

This will bring up a command line interface with options to stitch videos coming
from USB cameras or to stitch static videos. 
