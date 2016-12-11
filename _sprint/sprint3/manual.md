---
layout: page
title: Manuals
---


These manuals are operating under the assumption that the users and administrators will be utilizing the product of Sprint 2, not the entire finished product
## User Manual

- Prerequisites:
  1. Python 2.7
  2. Opencv 2.4 python library
  3. 2+ USB cameras
  4. Wowza cloud streaming engine server
  5. FFmpeg 3.1.4 software package for Python installed

- Set up:
  1. Install the dependencies by running the command: make install
  2. Generate the setup profile by running the command: make configure
  3. Follow the command line prompt to establish all configuration settings on your machine
  4. Put all images in the directory "data/sources" and all videos in "data/video"
  5. Attach cameras to USB ports on your machine
  5. Run the following command to finish the configuration setup: make run

- Running:
  - Follow the command line prompt to either stitch videos from cameras, stitch local images, stitch local videos, stream stitched videos, check streams, or preview streams
      - Stitch videos from cameras will take in streams, compute a homography and stitch frames together where they will be displayed in an opencv window
      - Stitch local images will take specified image files, compute a homography, stitch them together, and output the result as a static image in a new window.
      - Stitch local videos will take configured video files, compute a homography, stitch frames together and output the result to a new windo for viewing.
      - Stream stitched videos will take input from camera streams, compute a homography, stitch frames together, pipe them to ffmpeg where they will be sent over an rtmp stream to our wowza server.
      - Check streams will tell you whether the specified camera index is valid
      - Preview streams will allow you to view the unaltered live feed from the specified camera index.

- Troubleshooting:
  - Make sure video and image files are in the correct folder listed above in the set up section. If not, then they will not be found by the script.
  - Check your USB port numbers when you are making the configuration file, make sure that the port number corresponds to the stream coming in.
  - When filming, make sure the cameras are level and have significant overlap in their field of view. If not, then the script will not be able to stitch the two streams properly.
  - Make sure you have configured the correct ordering of camera indexes, i.e. left index is really on the left


- Viewing live stream on Wowza:
  1. Make sure you have a Wowza server up and running with a new application that can take live stream (see Admin manual to set this up)
  2. Go to the Wowza streaming engine manager (http://54.208.55.156:8088/enginemanager) and click on the application "live".
  3. Click incoming streams on the left tab bar and select "myStream".
  4. Then click "Test Player" to see the cameras being streamed to the Wowza server


# Administrator Manual

### Stitching

- Documentation:
  - Run the following command to generate documentation: make html
  - Run the following command to lint the code: make lint
  - Run the following command to test the code: make test

### Streaming

- Wowza:
  - We have set up a Wowza streaming engine free trial on an AWS server. To gain administrative rights please contact us directly (we don't want to put secure passwords on the web).
  - To set up a new live application go to the "Applications" tab on the top of the engine manager page. Click the tab on the left that says "Add Application" and follow the prompts to configure settings.
  - Right now we have our Application configured to accept any rtmp stream, and you can change these settings in the tab that says "Source Security"
