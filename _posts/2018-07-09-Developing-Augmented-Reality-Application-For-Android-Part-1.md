---
layout: post
title: Developing Augmented Reality Application For Android (Part 1)
tags: [All Things Tech]
image: /public/images/edmunds-technology.png

bio: Denys Vorontsov is a Senior Software Engineer at Edmunds.com
 
#this can be a jpg/png/gif or any other image type format#
biopic: dvorontsov-pic.jpg

featured-summary:
    <p>This is our first post as part of a series discussing the journey of developing <i>Can It Fit?</i> , an Augmented Reality experience for Android and iOS.  In this post we introduce the product and discuss our development approach, specifically for Android. We also talk about some challenges we faced and how we overcame them.</p>
    

summary: This is our first post as part of a series discussing the journey of developing <i>Can It Fit?</i> , an Augmented Reality experience for Android and iOS.  In this post we introduce the product and discuss our development approach, specifically for Android. We also talk about some challenges we faced and how we overcame them.

---


## Introduction
<i>Can It Fit?</i> is an [Augmented Reality](https://en.wikipedia.org/wiki/Augmented_reality) (AR) experience where a user can see how a car of their choice fits in a parking space.  It's currently available in Edmunds for [iOS](https://itunes.apple.com/us/app/edmunds/id393630966?mt=8) and [Android](https://play.google.com/store/apps/details?id=com.edmunds&hl=en_US).  In a series of articles, we will discuss the journey we took to develop <i>Can It Fit?</i>

<i>Can It Fit?</i> was conceived as proof of concept for multiple AR-capable devices that were in development stage (Microsoft Hololens and Google Tango).  Shortly after Apple announced ARKit, the team decided to focus on an iOS implementation and released <i>Can It Fit?</i> on iOS in August 2016. Most recently, we ported <i>Can It Fit?</i> to Android, using [ARCore](https://developers.google.com/ar/discover/) - Google’s platform that utilizes device capabilities to bring users augmented reality experience.  This series of articles focuses on the journey of porting <i>Can It Fit?</i> experience to Android.

<i>Can It Fit?</i> requires the user to follow these steps:
* Scan the environment to find horizontal floor plane
* Draw a rectangular area to designate the parking space (may include setting the height to form a box)
* Choose a vehicle.  Once chosen, a generic 3D model of the vehicle is scaled to proper dimensions and placed in the scene right in the center of the “parking spot”
* (Optional) Rotate the vehicle 90 degrees


<img src="{{site.baseimagesurl}}/can-it-fit/app-flow.gif" height="600" />

<br>
## Prototype
As you could see from the above instructions, the main AR components are a box (representing the parking space) and a vehicle.  Our initial goal was to build a prototype Android app that implements both of these components and the interaction between them.  The prototype was expected to do the following:
* Load vehicle model assets (meshes and textures)
* Detect floor plane
* Draw a box from user input
* Place a vehicle in the center of the box and match orientation of the box
* Detect collision between box faces (except the “floor” face) and vehicle meshes.

When we began working on the prototype, we used one of Google’s example projects and kept modifying it until it fit our requirements.  That way the code was separate from our Android codebase,  and we did not have to worry about making mistakes.  This decision allowed us to iterate quickly and fail fast.  The code base was very experimental, sometimes containing multiple solutions for a single problem (for the benefit of comparison).  The code architecture was fairly undefined and most of the code resided in a single class.  

<br>
## Architecture
We decided to split the work into two separate components: User Interface (UI), which controls the user flow and stage transitions and the Augmented Reality engine, which does the rendering and updates the logic.  The UI component is simply a native Android integration, whereas the AR engine required more platform-agnostic computer graphics knowledge.

Once the prototype app met its requirements and the entry point to <i>Can It Fit?</i> was implemented in the Edmunds Android app, the two were integrated into a single code base.  Specifying a clean interface helped make the integration very smooth.  To keep the interface lean, we made sure to identify a minimum set of actions that the UI component may need to perform.  Everything else was hidden in the implementation.

<img src="{{site.baseimagesurl}}/can-it-fit/architecture.png"  />

<br>
## Libraries
Today, ARCore can be supplemented with [Sceneform](https://developers.google.com/ar/develop/java/sceneform/), a library that abstracts away graphics drawing API and other ARCore consideration.  It also adds a useful math library, scene-graph API, and asset loading among other things.  Unfortunately for us, Sceneform didn’t yet exist when we began working on the prototype.  We were responsible for writing code required to process computer graphics and draw to the screen using [OpenGL ES](https://www.khronos.org/opengles/).  Our <i>Can It Fit?</i> code quickly became consumed with OpenGL ES calls, shaders, and arrays of float values representing geometric vertices and indices.  At this point we determined that our <i>Can It Fit?</i> implementation was no longer viable for long-term maintainability.

When Google released Sceneform, it became clear that it would ease many of our pain points and let us focus on application logic.  We immediately jumped on migrating the prototype.

<br>
## Conclusion
In this first article of the series, we covered <i>Can It Fit?</i> user flow, building the prototype, and the architecture.  We also touched upon our choice of Sceneform as the library to handle lower-lever considerations.  In future articles, we will break down development with additional detail.
