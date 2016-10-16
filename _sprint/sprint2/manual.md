---
layout: page
title: Manuals
---


These manuals are operating under the assumption that the users and administrators will be utilizing the product of Sprint 1, not the entire finished product
## User Manual
### Stitching

- Prerequisites:
  1. Python 2.7
  2. Opencv 2.4 python library
  3. 2+ USB cameras

- Set up:
  1. Install the dependencies by running the command: make install
  2. Generate the setup profile by running the command: make configure
  3. Follow the command line prompt to establish all configuration settings on your machine
  4. Put all images in the directory "data/sources" and all videos in "data/video"
  5. Attach cameras to USB ports on your machine
  5. Run the following command to finish the configuration setup: make run

- Running:
  1. Follow the command line prompt to either stitch videos from cameras, stitch local images, stitch local videos
  2. The script with begin and the frames will be outputted to an opencv window where they can be viewed

- Troubleshooting:
  - Make sure video and image files are in the correct folder listed above in the set up section. If not, then they will not be found by the script.
  - Check your USB port numbers when you are making the configuration file, make sure that the port number corresponds to the stream coming in.
  - When filming, make sure the cameras are level and have significant overlap in their field of view. If not, then the script will not be able to stitch the two streams properly.

### Streaming

- Prerequisites:
  1. All components of a working stitching script as documented above
  2. A Wowza cloud streaming engine server
  3. FFmpeg 3.1.4 software package for Python

- Set up:
  1. Make sure the port number is configured in profile.yml
  2. Run the command: make client
  3. This will stream to a local port where client.py is listening to the incoming stream. This will later transform into the Wowza server listening to the stream

- Uploading to Wowza:
  1. Right now we can only support uploading to Wowza from a static mp4 file or an unstitched stream.
  2. Make sure you have a Wowza server up and running with a new application that can take live stream (see Admin manual to set this up)
  3. Run the following command from the root directory of the stitching repository: ffmpeg -re -i data/videos/cam1.mp4 -c copy -f flv rtmp://localhost:1935/live-test/myStream
  4. Go to the Wowza streaming engine manager (http://localhost:1935/enginemanager) and click on the application "live-test".
  5. Click incoming streams on the left tab bar and select "myStream".
  6. Then click "Test Player" to see the static video being streamed to the Wowza server


# Administrator Manual

### Stitching

- Documentation:
  - Run the following command to generate documentation: make html
  - Run the following command to lint the code: make lint
  - Run the following command to test the code: make test

### Streaming

- Set up:
  1. Set up Wowza streaming engine by downloading free trial from the Wowza website and follow online installation instructions
  2. Go to the Wowza engine manager web interface and create a new application called "live-test"
  3. Now you should be able to send and receive live streams at this port.

  
