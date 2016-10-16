---
layout: page
title: Test Plan
---

## Ideal Plan

- Unit Tests:
  - Use unit tests to systematically measure the functionality of the python stitching script.
  - Unit test the homography matrix with different image sets.
  - Unit test the keypoint detection for individual images of different brightness, size, etc.
  - Unit test the keypoint matching between multiple images.
  - Unit test the output frames of the stitching script with different image sizes to see the accuracy of the stitching
  - Unit test the configuration using streams of different quality, sizes, and on different systems.
  - Unit test the rtmp connection to a server
  - Unit test the encoding of videos of different sizes and qualities

- Integration Tests:
  - Test the connections between the driver file (run.py) and the stitching module (panorama.py)
  - Test the system with different numbers of cameras
  - Test with still images, video files, and video streams.
  - Test the connection between the RTMP stream and the stitching script

- Acceptance Tests:
  - Look at the full output videos of stitched streams and test the quality
  - Does the script take 4 video streams, create a homography matrix by matching key points, and stitching 4 streams together?
  - Does the python script take a stitched video and stream it over RTMP to a server?


## Actual Plan

- Configuration Tests:
  - Script should be able to initialize 4 video streams
  - Test that all video streams are visible and without errors

- Stitching Tests:
  - Use different sets of mp4 video files to stitch together and examine the output.
  - Look for missing video streams, stitching errors, warping, and poor resolution.

- Encoding Tests:
  - Check that an RTMP stream can be established to a server
  - Test sending video files over RTMP stream to Wowza server
  - Check encoding to ensure that correct parameters were provided and quality was maintained on the video files

- Integration Tests:
  - Test the connection between video streams and stitching script. Ensure that all streams are inputting properly
  - Test the connection between the stitching script and the encoding process. The stitched video stream should be encoded and sent over an RTMP server.
  
