---
layout: page
title: Manuals
---

These manuals are operating under the assumption that the users and administrators will be utilizing the product of Sprint 4, not the entire finished product
## User Manual

For setting up the required software on the Jetson TX1, use our provisioning [scripts](https://github.com/360ls/provision.git).
We assume that the Jetson has been provisioned and set up properly in the
following steps.

- Prerequisites:
  1. Python 2.7
  2. Opencv 2.4 python library
  3. 2+ USB cameras
  4. Wowza cloud streaming engine server
  5. FFmpeg 3.1.4 software package for Python installed
  6. Jetson board with Ubuntu 14.04 installed


- Set up (Desktop Application):
  1. Make sure all dependencies are installed on the box before you try to run the application
  2. Download the desktop application from our github page [here](https://github.com/360ls/desktop/releases)
  3. You can find detailed instructions on how to install and run the code [here](https://360ls.github.io/360ls/sprint/sprint4/code)
  4. Run `sudo dpkg -i 360ls-Desktop-Application-1.0.0-amd64.deb`.


- Set up (Web Application):
    1. Navigate to our web application after you streamed a video to see it playing live [here](https://vcms.herokuapp.com/player)



- Set up (Stitching Application):
    1. Make sure you have the correct versions of OpenCV and Python installed.
    2. Clone the stitch-flex repository by running the command:
    `bash
    git clone https://github.com/360ls/stitch-flex.git
    `


  - To install the package:

  `bash
  cd stitch-flex
  git checkout origin checkpoint/sprint3
  make clean-install
  `

  - This will install package dependencies via npm (node.js) and pip (python), including the yarn package manager dependency.


- Running (Desktop Application):
  - Use the tab bar in the upper left of the app to navigate between the DVR mode, Live mode, and Preferences
  - On the Live page you can press 'Record' and a live recording will start with the cameras attached to the box
  - This recorded video will be live streamed to our Wowza server and routed to the web application for live viewing.
  - Once you are done recording press 'Stop Recording' and the recording will be stopped and the video will be saved and uploaded to our web application.
  - You can then navigate to the DVR page where you will see a table of videos that have been saved.
  - Click on on of these videos and you will be taken to a player that will display the video while also providing information on the time and duration. Users will have the option to flag a video if it needs further inspection.
  - Navigate to the Preferences page to change settings of the application.

- Running (Stitching Application):

  - To run the app, either:

  `bash
  make run
  `
  - to simply run the app

  OR

  `bash
  make
  `

  - to clean the package, do a fresh (but not brand new) install of dependencies, and then run the app.

  - To run the cli, which provides the most functionality.:
  `bash
  make cli
  `

  - To set up the camera streams
  `bash
  make camera-setup
  `

  - To demonstrate threading through taking snapshots
  `bash
  make snap
  `

  - To lint the application:

   - For JS files:
  `bash
  eslint nameoffile.js
  `

   - For Python files;
  `bash
   make lint-py
  `

  - To run tests against the application:

  `bash
  make test
  `


- Troubleshooting:
  - Make sure video and image files are in the correct folder listed above in the set up section. If not, then they will not be found by the script.
  - Check your USB port numbers when you are making the configuration file, make sure that the port number corresponds to the stream coming in.
  - When filming, make sure the cameras are level and have significant overlap in their field of view. If not, then the script will not be able to stitch the two streams properly.
  - Make sure you have configured the correct ordering of camera indexes, i.e. left index is really on the left
  - The cameras should be in live feed mode, not playback mode.
  - The cameras should not be in fish eye mode.
  - Verify all of the dependicies have been correctly installed with the correct version numbers.


- Viewing live stream on Wowza:
  1. Make sure you have a Wowza server up and running with a new application that can take live stream (see Admin manual to set this up)
  2. Go to the Wowza streaming engine manager (http://54.208.55.156:8088/enginemanager) and click on the application "live".
  3. Click incoming streams on the left tab bar and select "myStream".
  4. Then click "Test Player" to see the cameras being streamed to the Wowza server


# Administrator Manual

### Desktop Application
- Follow the instructions [here](https://github.com/360ls/desktop/blob/master/README.md) to set up a developer environment for the electron app.
- We are using the Yarn package manager to install all dependencies for the app so make sure you have the latest version installed as well as Node.js and the npm package manager.

### Web Application
- Wowza:
  - We have set up a Wowza streaming engine free trial on an AWS server. To gain administrative rights please contact us directly (we don't want to put secure passwords on the web).
  - To set up a new live application go to the "Applications" tab on the top of the engine manager page. Click the tab on the left that says "Add Application" and follow the prompts to configure settings.
  - Right now we have our Application configured to accept any rtmp stream, and you can change these settings in the tab that says "Source Security"
  - [Here](https://docs.google.com/document/d/1P3ktqEnJgV6XPH9jGXVkZrj0uZQlp852OA8L4wnukl0/edit) is a link to our documentation on accessing the Wowza Streaming Engine over SSH. This is needed to start and stop the app as well as configure both the AWS instance and the Wowza instance.

- AWS S3:
  - Here (https://docs.google.com/document/d/1ap1i3Up0t6JJovi1SbXU570-4pcEgIIDbZy8u_Et4z0/edit) is a link that shows how to set up your development environment to work with our development bucket on S3 so you can develop against it.
