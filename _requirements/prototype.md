---
layout: page
title: Prototype
---

Our prototype can be found at the following links.

[Video Stitcher Prototype](https://github.com/dongy7/360ls-stitcher)

The prototype is a realtime stitcher that can be configured to work with a 2 camera setup. It uses OpenCV to detect keypoints and compute the homography matrix.
The stitcher uses the homography matrix to stitch together the two streams into a single stream.

[Web App Prototype](http://vcms.herokuapp.com/)

The prototype consists of a full-stack python Django environment hosted in a Heroku instance. For the prototype, we hooked into our [main project inventory](https://github.com/ASK-MEdia/360ls-vcms) and tied in a CircleCI build driver that builds dynamically from updates to the master branch of our GitHub profile. The prototype dependencies are packaged in a custom vagrant build for consistent development and testing on our local devices.
