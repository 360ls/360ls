---
layout: page
title: Use Cases
---

This portion of the website highlights the use cases portion of the functional specification for the requirements sprint. The use cases are broken down by application (i.e. the on-box app and the dvr web app).


## Web Application
- Login
	- First time user creates an account
	- Repeat users enter a username and password
	- If a user forgets their password, they can reset it
	- If a user enters a wrong password, an error is displayed and another password is requested

- Filter Live Videos
	- Filter the visible live videos to look for a specific officer's live feed

- Watch Live Video
	- Pan around the 360 video

- Filter Archived Videos
	- The user can scroll through a list of all vidoes
	- Filter to find by date, or officer ID

- Watch Archived Video
	- Pan around the 360 video
	- Pause the video
	- Rewind the video

- Export Video
	- Save the video locally as a file for export
	- Provide a name for the file

- Logout
	- Press button to sign out of an account
	- Prompt to log in as a different user

## On-box Linux Application
- Login
	- Upon entering the car, user enters a username and password
	- If a user forgets their password, they can reset it
	- If a user enters a wrong password, an error is displayed and another password is requested

- Watch Live Video
	- See the situation around the car from a live no-latency feed on the in-car box.

- Filter Archived Videos
	- The user can scroll through a list of all vidoes associated with their account
	- Filter to find by date, etc.

- Watch Archived Video
	- Pause the video
	- Rewind the video

- Manually Start and Stop Recording
	-The user can toggle between a recording and docile state

- Logout
	- Press button to sign out of an account
	- Prompt to log in as a different user

- Display a Stitched Video (use case of program to enable watching live video)
	- Take video input from four camera streams and stitch it into one video
	- Convert that stitched video into multiple encodings of a 360 degree video

- Stream Video (use case of program to enable streamed video in on-box and web applications)
	- Send stitched video to a server for storage
	- Live stream stitched video from server storage and live device stitched footage


