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


## Web Application
To use the web application, go [here](https://vcms.herokuapp.com).

## Stitcher Application

### Clone the stitcher repository

```bash
git clone https://github.com/360ls/stitcher.git
```


### To install the package:

```bash
cd stitcher
git checkout origin results/final
make install
```

This will install package dependencies via pip (python)

### Then, to run the app

```bash
make run
```

### To run the cli, which allows for testing and development utilities
```bash
make cli
```
-------

## Developing and Building the Desktop Application

You can find the instructions for setting up a developer
environment for the desktop application [here](https://github.com/360ls/desktop/blob/master/README.md).
