---
layout: page
title: User Stories and Use Cases
---

## User Stories
1. I am a district attorney and I deal with a lot of cases with video evidence from the field captured by the police. I want a simple web interface that allows me to search for a particular video recorded at a certain time and view it on demand. I need to be able to save certain sections of a video so that I can go back to it and present the evidence in a trial.
2. As a patrolling police officer, I can view a live-stream video of on-car video from an in-car touch-screen on the streaming device. 
3. As a patrolling police officer, I can view all video in a web DVR offering for incidents with which I was involved.
4. As a patrolling officer, I can search for videos by time-of-incident, and tags that I set up to correspond to time-of-incident. 
5. As a patrolling officer, in the DVR player, I can manipulate video quality to get a better stream on a poor connection, and I can zoom in on different areas of the video.
6. One of Scott’s officers has just returned from an incident and Scott is performing an evaluation on his performance, so he navigates to the 360LS web interface to view the video of the interaction. He logs in using his police chief credentials and searches for the video from his officer’s car. Scott examines the video by panning around the screen and at some points pausing and rewinding the video to get a better look at the scene. He takes some notes to share with his officer and exits the system.

## Use Cases Derived from User Stories
- Login
	- First time user creates an account
	- Repeat users enter a username and password
	- If a user forgets their password they can reset it
	- If a user enters a wrong password it should display an error

- Search Live Videos
	- Use a search bar to look for a specific car or officer's live video

- Watch Live Video
	- Pan around the 360 video

- Search Archived Videos
	- The user can scroll through a list of all vidoes
	- Use a search bar to find by date, or car number, or officer ID

- Watch Archived Video
	- Pan around the 360 video
	- Pause the video
	- Rewind the video
	- Write comments or notes on the video

- Export Video
	- Save the video locally as a file for export
	- Provide a name for the file

- Delete Videos
	- User presses a delete button on the video to remove a file from the storate
	- The system will prompt to make sure the user really wants to delete

- Logout
	- Press button to sign out of an account
	- Prompt to log in as a different user
