---
layout: page
title: Executable Code and Instructions
---

## Desktop Application

### Hardware Setup

Our application is designed to be used on the [Jetson TX1](http://www.nvidia.com/object/jetson-tx1-module.html) hardware.

For our setup, we installed [Jetpack 2.1](https://developer.nvidia.com/embedded/jetpack-2_1). At the moment later versions are not supported because electron does not support ARM64 architecture currently.

Pull down our [repository](https://github.com/360ls/provision.git) that contains the provisioning scripts.

```sh
$ git clone https://github.com/360ls/provision.git
```

Run the installer that will install [Ansible](https://www.ansible.com/).

```sh
$ make install
```

Run the provisioning script:

```sh
$ make provision
```

*NOTE*: This step can take up to an hour as it will compile and install
OpenCV from the source.

When the provisioning step is done, run the test script
to make sure the `OpenCV` functionalities are working. A working
usb camera needs to be connected for this step.

```sh
$ make test
```
You can find the latest executables [here](https://github.com/360ls/desktop/releases).

### Running the Desktop Application

1. Download the latest zipped release.
2. Unzip with `unzip 360ls-x.y.z-armv7l.zip`, where `x.y.z` is the latest version number.
3. Run the executable called `360ls` inside the unzipped directory.


## Web Application
To use the web application, go [here](https://vcms.herokuapp.com).

## Stitcher Application

### Clone the stitcher repository

```sh
$ git clone https://github.com/360ls/stitcher.git
```


### To install the package:

```sh
$ cd stitcher
$ git checkout origin results/final
$ make install
```

This will install package dependencies via pip (python)

### Then, to run the app

```sh
$ make run
```

### To run the cli, which allows for testing and development utilities
```sh
$ make cli
```
-------

## Developing and Building the Desktop Application

You can find the instructions for setting up a developer
environment for the desktop application [here](https://github.com/360ls/desktop/blob/master/README.md).
