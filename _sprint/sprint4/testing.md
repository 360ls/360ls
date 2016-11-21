---
layout: page
title: Test Plan
---

## Ideal Plan

## Unit Tests:
### Stitching:
  - Use unit tests to systematically measure the functionality of the python stitching script.
  - Unit test the barrel distortion fixes that we made this sprint. Can we correctly calibrate the videos to reduce fish eye and barrel distortion?
  - Unit test the remapping of the calibrated images
  - Unit test the efficiency of the stitching algorithm. Are we stitching quickly enough to establish a true live stream.

### Streaming:
  - Unit test the speed of the encoding. Is ffmpeg reading and encoding at a rate that is acceptable to produce a smooth live stream?
  - Unit test calibration of 4 live camera feeds.
  - Unit test the configuration using streams of different quality, sizes, and on different systems.
  - Unit test the rtmp connection to the AWS hosted Wowza server
  - Unit test playing a video on our web app

### Desktop:
  - Unit test recording a video on the Desktop application
  - Unit test saving a video from the Desktop
  - Unit test uploading a video to the AWS server from the desktop
  - Unit test changing the preferences
  - Unit test sorting the videos and filtering by flag, date, time.
  - Unit test playing a video back on the desktop.
  - Unit test flagging a video
  - Unit test establishing an rtmp connection from the desktop

## Integration Tests:
  - Test the piping of images from python stitching module to the ffmpeg encoding. Do the output images from the stitching get correctly piped from our module to the ffmpeg rtmp stream?
  - Test sending a live stream from the desktop to the Wowza engine
  - Test the configuration of 4 live camera streams into our stitching module. Can the stitching script produce a video of 4 cameras stitched together?
  - Test the connection between AWS wowza server and our web app. Can we receive a live stream video onto our Django/Python app?
  

## Acceptance Tests:
  - Test our installation process for the desktop app. Can we successfully install our electron app onto the Jetson board following our instructions?
  - Test viewing an output video from 4 live cameras stitched together. Look for things like low quality, lagging, warped around the sides, misalignment.
  - Test the live streaming from 4 cameras. Test for discoloration, lagging, jumpiness, buffering, etc.
## Final Test
  - Does the desktop app take 4 live inputs, stitch them together, stream them over rtmp to wowza server, and push to a player on our web app where we can view the stream?


# Actual Plan

- Configuration Tests:
  - Script should be able to initialize 4 video streams
  - Test that all video streams are visible and without errors
  - We should be able to install the desktop app onto the Jetson board

- Stitching Tests:
  - Use 4 video streams to test the quality of the stitching.
  - Look for missing video streams, stitching errors, warping, and poor resolution.
  - Test the efficiency of the stitching, is there lagging, jumpiness, etc.?
  - Test the barrel distortion correction fixes that we made this sprint.

- Encoding Tests:
  - Check that an RTMP stream can be established to a server
  - Test sending video files over RTMP stream to Wowza server
  - Test sending a live stream video over RTMP to wowza server

- Streaming Tests: 
  - Test viewing a live streamed video on the Wowza server.
  - Look for errors like lagging, jumping, discoloration, buffering, etc.
  - Test viewing a video on the web app
  - Test viewing a live stream video pushed from the Wowza server to the web app

- Desktop Tests:
  - Recording a video on the Desktop application
  - Saving a video from the Desktop
  - Uploading a video to the AWS server from the desktop
  - Changing the preferences
  - Sorting the videos and filtering by flag, date, time.
  - Playing a video back on the desktop.
  - Flagging a video
  - Establishing an rtmp connection from the desktop

- Integration Tests:
  - Test taking 4 live streams, stitch them together, pipe the output to ffmpeg, encode these frames into rtmp, push this stream to a wowza server, and view the live stream on our web app. 
  
