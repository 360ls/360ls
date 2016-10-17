---
layout: page
title: Functional Specification - Sprint 2
---

This portion of the website highlights the functional specification for the second development sprint. This functional specification includes use cases, requirements, and interfaces targeted and achieved during that sprint. 

# Use Cases

## Use Cases Targeted

### On-box Application
- Display a Stitched Video (use case of program to enable watching live video)
	- Take video input from four camera streams and stitch it into one video
	- Convert that stitched video into multiple encodings of a 360 degree video 
	- Send 360 degree video to server to interact with wowza streaming service
- Stream Video (use case of program to enable streamed video in on-box and web applications)
	- Send stitched video to a server for storage
	- Live stream stitched video from server storage and live device stitched footage
- Watch Live Video
	- See the situation around the car from a live on-latency feed on the in-car box.
	- See live video in a simple player in the web application

## Use Cases Realized

### On-box Application
- Display a Stitched Video (use case of program to enable watching live video)
	- Take video input from two camera streams and stitch it into one stream
	- Take video and image input from four local sources and stitch together
- Stream Video (use case of program to enable streamed video in on-box and web applications)
	- Send stitched video to server via RTMP stream
	- Live stream stitched video from Wowza streaming tools player.
 

## Summary of Use Case Fulfillment
During Sprint 2, we sought to build upon our stitching script so that it could stitch together 4 camera streams into one 360 degree video. We also set a goal to save multiple encoded video files to local disk, as well as create the cabapility to pipe stitched footage to an RTMP stream for delivery to the wowza streaming service and player. After completion of Sprint 2, our stitching algorithm is by now means perfect, and we still cannot quite stitch and send four streams, we are much closer to a complete process than we were before. As a result of this sprint, we were able to complete the majority of our Display a Stitched Video use case and the Stream Video use case. One of the things that we ran into that was unexpected, and we are now solving for, was the radial distortion of our input lenses. So we took a good chunk of time trying to get distortion correction fixed and solved for, but we couldn't get it as far as we would have liked. For that reason, we will be going to some of the faculty in the department to try and get the problem resolved. 

# Requirements
 
## Requirements Targeted
At the beginning of Sprint 2, we prioritized our requirements for the sprint as follows (with prioritization representing order of approach, not necessarily in order of project value):

### Priority 1
- The Box
	- Stitch 4 videos together and save them locally.
		- Completed stitching script for local and camera inputs.
		- Set up hardware to process 4 video streams for consumption in the stitching script
	- Set up a file system to store videos locally
	- Implement different encodings on-box to figure out best way to optimize live streaming process
	- Improve stitching algorithm to work well with 4 live video streams
	- Set up a way to manage streams programatically in Wowza

### Priority 2
- The Box
	- Set up Electron app to begin development on managing local videos.
	- Set up the encoding of 360 video and establish player we plan to use.
- Server-side Implementation
	- Install Wowza on Heroku or AWS instance and view streams in their embedded player.

## Requirements Realized
After completion of Sprint 2, we were able to complete the following requirements. We got very close to completing all of the requirements we needed to complete. 

### Priority 1
- The Box
	- Stitch videos together and save them locally.
		- Completed stitching script for local and camera inputs.
		- Set up hardware to process 4 video streams for consumption in the stitching script
	- Implement different encodings on-box to figure out best way to optimize live streaming process

### Priority 2
- The Box
	- Set up Electron app to begin development on managing local videos.
	- Set up the encoding of 360 video and establish player we plan to use.
- Server-side Implementation
	- Install Wowza on Heroku or AWS instance and view streams in their embedded player.


# Interfaces
We did not target completion of any of the interfaces affiliated with the completion of our app during this specific sprint, but we did end up developing a small electron application that opens up a web view to our project website.







