---
layout: page
title: Platform Analysis and Selection
---

*What we need*
We have identified two cases in which solutions need to be developed. The first is an Nvidia
Jetson box that runs an Ubuntu variant. It will be located within vehicles. We must also
develop a way for users to view recordings and live video outside of the vehicle.

*Our Selection*
* Ubuntu App
    1. *Electron App*
        An electron app can be built using familiar technology (HTML, CSS, and Javascript). 
        We hope to reuse components from our web app (discussed below).
        http://electron.atom.io/
    2. Native Linux GUI
        We could alternatively build a GUI with something like Qt framework that will allow
        us to use C++. However it is technology that we are less comfortable with and seems 
        less intuitive for our simple UI.
        http://en.wikipedia.org/wiki/Qt_(software)

* App for viewing video beyond the box:
    1. *Web App*
        We could build a responsive web app that will deliever good UX on all devices (computer,
        tablet, phone). It will allow for simpler development because we must build only one
        application, and it is the platform our team has the most experience with. We will 
        use Django because we have some limited experience with the framework and an outside
        of the class team member is a Django expert should we encounter and difficulties.
        Alternatively we could go without a framework with PHP/ MySQL or use Rails but
        our collective knowledge of those technologies does not justify their use over Django
        when we have an expert at our disposal.
    2. Native apps (iOS and Android) + Web app
        Building native apps could lead to a better experience for our users that view media
        on phones or tablets, however the increased development effort outweighs the benefit.
