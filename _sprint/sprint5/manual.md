---
layout: page
title: Manuals
---

# User Manual

For setting up the required software on the Jetson TX1, use our provisioning [scripts](https://github.com/360ls/provision.git).

We assume that the Jetson has been provisioned with our scripts in the following steps.

## Pre-requisites

The following software and applications are needed to run our application:

1. Python 2.7
2. Opencv 2.4 with Python bindings
3. 2+ USB cameras
4. Wowza cloud streaming engine server
5. ffmpeg 3.2.x
6. Jetson TX1 board with Jetpack 2.1


## Setup

### Desktop Application

1. Download the desktop application from our Github page [here](https://github.com/360ls/desktop/releases)
2. You can find detailed instructions on how to install and run the code [here](https://360ls.github.io/360ls/sprint/sprint5/code)
3. Unzip the release and open the binary called `360ls`.

### Web Application

1. Navigate to our web application after you streamed a video to see it playing live [here](https://vcms.herokuapp.com/player)



### Stitcher Application

1. Make sure you have the correct versions of OpenCV and Python installed.
2. Clone the stitcher repository: `git clone https://github.com/360ls/stitcher.git`.
3. Install the dependencies: `make install`.

## Running

### Desktop Application
- Use the tab bar in the upper left of the app to navigate between the DVR mode, Live mode, and Preferences
- On the Live page you can press 'Record' and a live recording will start with the cameras attached to the box
- This recorded video will be live streamed to our Wowza server and routed to the web application for live viewing.
- Once you are done recording press 'Stop Recording' and the recording will be stopped and the video will be saved and uploaded to our web application.
- You can then navigate to the DVR page where you will see a table of videos that have been saved.
- Click on one of these videos and you will be taken to a player that will display the video while also providing information on the time and duration. Users will have the option to flag a video if it needs further inspection.
- Navigate to the Preferences page to change settings of the application.

### Web Application

- Navigate to our [web application](https://vcms.herokuapp.com) to see saved videos or a live stream.
- Two tabs at the top of the screen denote which mode you are in either 'DVR' or 'Live'.
- Switch to 'Live' mode to see an incoming stream inside of the player. Pan around the player to view the stream as a rendered 360 video.
- Switch to 'DVR' mode to view all recorded videos.
- You will see the same player with a table below containing all saved videos and data on when they were uploaded, their flag status and whether they have been opened.
- Click on a video to see it appear in the player where you can pan around and view it as a rendered 360 video.

### Stitcher Application

- To run the app run the following command:
```sh
$ make run
```

- To run the cli, which provides the most functionality:
```sh
$ make cli
```

- To run utility functions:
```sh
$ make utils
```

## Troubleshooting:

### Stitching Application:

- Make sure video and image files are in the correct folder listed above in the set up section. If not, then they will not be found by the script.
- Check your USB port numbers when you are making the configuration file, make sure that the port number corresponds to the stream coming in.
- When filming, make sure the cameras are level and have significant overlap in their field of view. If not, then the script will not be able to stitch the two streams properly.
- Make sure you have configured the correct ordering of camera indexes, i.e. left index is really on the left
- The cameras should be in live feed mode, not playback mode.
- The cameras should not be in fish eye mode.
- Verify all of the dependencies have been correctly installed with the correct version numbers.

### Web Application:

- If there is no incoming stream verify that the desktop application is on and is currently in 'live' mode not 'record' or 'preview' mode.
- When viewing a live stream there is about 20-30 seconds of latency so don't be alarmed by delayed video
- Depending on your orientation of the camera, the scene being live streamed may not be in direct field of view in the player so you may have to pan around.


# Administrator Manual

## Desktop Application

Follow the instructions [here](https://github.com/360ls/desktop/blob/master/README.md) to set up a developer environment for the electron app.

## Web Application

### Development:

- We developed the application with a private repo under the organization ASK-MEdia/360ls-vcms on github. Please contact Steven King (info can be found on our contact page) if you need access to the development environment for this application.
- Follow the instructions on the README page in this repo for details on how to set up the development environment

### Wowza:

- We have set up a Wowza streaming engine free trial on an AWS server. To gain administrative rights please contact us directly (we don't want to put secure passwords on the web).
- To set up a new live application go to the "Applications" tab on the top of the engine manager page. Click the tab on the left that says "Add Application" and follow the prompts to configure settings.
- Right now we have our Application configured to accept any rtmp stream, and you can change these settings in the tab that says "Source Security"
- [Here](https://docs.google.com/document/d/1P3ktqEnJgV6XPH9jGXVkZrj0uZQlp852OA8L4wnukl0/edit) is a link to our documentation on accessing the Wowza Streaming Engine over SSH. This is needed to start and stop the app as well as configure both the AWS instance and the Wowza instance.

### Viewing live stream on Wowza:

1. Make sure you have a Wowza server up and running with a new application that can take live stream (see Admin manual to set this up)
2. Go to the Wowza streaming engine manager (http://54.208.55.156:8088/enginemanager) and click on the application "live".
3. Click incoming streams on the left tab bar and select "myStream".
4. Then click "Test Player" to see the cameras being streamed to the Wowza server

### AWS S3:

- Here (https://docs.google.com/document/d/1ap1i3Up0t6JJovi1SbXU570-4pcEgIIDbZy8u_Et4z0/edit) is a link that shows how to set up your development environment to work with our development bucket on S3 so you can develop against it.
