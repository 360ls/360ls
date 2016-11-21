---
layout: page
title: Executable Code and Instructions
---

## Desktop Application

### Hardware Setup

Our application is designed to be used on the [Jetson TX1](http://www.nvidia.com/object/jetson-tx1-module.html) hardware.

For our setup, we installed [Jetpack 2.1](https://developer.nvidia.com/embedded/jetpack-2_1). At the moment later versions are not supported because electron does not support ARM64 architecture currently.

Pull down our [repository](https://github.com/360ls/provision.git) that contains the provisioning scripts.

```bash
$ git clone https://github.com/360ls/provision.git
```

Run the installer that will install [Ansible](https://www.ansible.com/).

```bash
$ make install
```

Run the provisioning script:

```bash
$ make provision
```

*NOTE*: This step can take up to an hour as it will compile and install
OpenCV from the source.

Finally run our setup script:
```bash
$ make setup
```
You can find the latest executables [here](https://github.com/360ls/desktop/releases).

### Ubuntu/Debian
1. Download the debian release.
2. Run `sudo dpkg -i 360ls-Desktop-Application-1.0.0-amd64.deb`.

## Stitcher Application

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
