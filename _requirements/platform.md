---
layout: page
title: Platform Analysis and Selection
---

**What we need**:
We have identified two cases in which solutions need to be developed. The first is an Nvidia
Jetson box that runs an Ubuntu variant. It will be located within vehicles. We must also
develop a way for users to view recordings and live video outside of the vehicle.

**Our Decisions (final selections in bold)**

* Video Stitcher
    1. **OpenCV**:
        OpenCV is an open source library that implements various computer vision algorithms and provides
				wrappers for various languages such as Python, C++ and Java.
        We chose OpenCV because it provides the stitching algorithms that we need to construct our
        360 degree video. OpenCV is also optimized to support GPU acceleration and multi-core
        to create real-time applications. We will use the Python wrappers for OpenCV because
        we have much more experience with Python over C++, and since most of the processing work will be done
        by the OpenCV library, we don't expect much of a performance benefit by using C++. 
    2. MATLAB:
        MATLAB has a well-documented and easy-to-learn library for computer vision. However, since
        it is an interpreted language, it will be much harder to optimize for real-time stiching and encoding.

* Ubuntu App
    1. **Electron App**:
        An electron app can be built using familiar technology (HTML, CSS, and Javascript). 
        We hope to reuse components from our web app (discussed below).
        http://electron.atom.io/
    2. Native Linux GUI:
        We could alternatively build a GUI with something like Qt framework that will allow
        us to use C++. However it is technology that we are less comfortable with and seems 
        less intuitive for our simple UI.
        http://en.wikipedia.org/wiki/Qt_(software)

* App for viewing video beyond the box:
    1. **Web App**:
        We could build a responsive web app that will deliever good UX on all devices (computer,
        tablet, phone). It will allow for simpler development because we must build only one
        application, and it is the platform our team has the most experience with. We will 
        use Django because we have some limited experience with the framework and an outside
        of the class team member is a Django expert should we encounter and difficulties.
        Alternatively we could go without a framework with PHP/ MySQL or use Rails but
        our collective knowledge of those technologies does not justify their use over Django
        when we have an expert at our disposal. For building and rendering our UI, we will use React
        because it has a simpler component based model over a more complex framework like Angular.

    2. Native apps (iOS and Android) + Web app:
        Building native apps could lead to a better experience for our users that view media
        on phones or tablets, however the increased development effort outweighs the benefit.
