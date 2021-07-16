# Gaze Tracking Demos

**Purpose:** To inspire creativity in others to find meaningful applications for gaze tracking.

**Summary:** A conglomeration of AR experiences that showcase the power of gaze tracking. The experiences herein can be classified into two primary groups,  object manipulation or analytical applications. Each experience highlights a separate use case and is intended to inspire AR authors think about how gaze tracking could enhance their own AR experiences.

### **Table of Contents**

- [What is Gaze Tracking?](#what-is-gaze-tracking)
- [ThingMark for Viewing AR Experiences](#thingmark-for-viewing-ar-experiences)
- [Object Manipulation](#object-manipulation)
  - [Understanding Gaze Tracking Demo](#understanding-gaze-tracking-demo)
  - [Put That, There Demo](#put-that-there-demo)
  - [Simon Game Demo](#simon-game-demo)
- [Analytical Applications](#analytical-applications)
  - [Quantifying Gaze Duration Demo](#quantifying-gaze-duration-demo)
  - [Board of Colorful Labels Demo](#board-of-colorful-labels-demo)
  - [Ring of Colorful Labels Demo](#ring-of-colorful-labels-demo)
  - [Other Ideas for Analytics](#other-ideas-for-analytics)
 

## What is Gaze Tracking?

### Background Explanation

Before we jump right into an explanation of gaze tracking, it is important that you understand a little bit about how the position and orientation of objects are defined in a virtual 3D space. To start off, virtually positioning an object in a 3D environment isn't something that was invented for augmented reality. It has actually been around much longer and is widely used in almost every video game you have ever played. It is what allows the computer to keep track of your character and the other objects in the environment and is crucial as you move throughout the virtual area.

In order to define an object's position, the computer must know the object's location and which way it is facing. The location data typically come in the form of 3-dimensional coordinates *(X,Y,Z)*, while the orientation data are commonly a set of angles or orthogonal vectors. These data fully-define any object in 3D space and are essential for a realistic rendering of the virtual environment.

### Position & Orientation in Vuforia 

Vuforia Engine defines objects within the augmented reality space using these same principles. Every object that is placed into the AR experience must have both its position and orientation defined. With this definition, the AR exprience is rendered consistently, no matter where the user is viewing from. Every widget (e.g., model, model item, 3D label) can be given X,Y,Z-coordinates, as well as X,Y,Z-rotations.

The user's position and orientation are also defined out of necessity and are constantly changing as they move through the AR space. These definitions are always made to track the user's device, whether it be a mobile device, or an AR headset. In contrast to the angles used for the other objects in the experience, the user's orientation is defined by a pair of orthogonal vectors. In the image below, the user's 3D coordinates relative to the experience origin are represented by the yellow point. The blue vector is normal to the user's device screen and represents the direction in which they are looking. The green vector is orthogonal to the blue and points vertically out of the device. It tells how the user's device is rotated about the blue vector and defines the remaining critical information.

<img width="450" alt="3D Position   Orientation" src="https://user-images.githubusercontent.com/86619231/125130156-c1374e00-e0bd-11eb-84a8-00e8cefb6635.png">


By figuring out how to access this complete set of data, we could know exactly where the user is and where they are looking in realtion to the objects in the AR experience. This knowledge would allow us to take our AR experiences to the next level by using the user's position and gaze to find out more about what they are actually seeing. We can use these data to manipulate the objects in the experience or perform analysis and learn more about the users.

## ThingMark for Viewing AR Experiences

The AR experiences described below can all be viewed by scanning this ThingMark with the Vuforia View app:

<img width="300" alt="ThingMark" src="https://user-images.githubusercontent.com/86619231/125703339-dea6da9a-ef52-420b-8ef5-9cd0fcf38b19.png">

## Object Manipulation

One of the potential use cases for gaze tracking is to employ data about the user's gaze to manipulate objects within the AR space. There are endless applications in which the ability to change an AR experience based on what the user is seeing would be beneficial. Listed below are some simple demos to show potential use cases and inspire your creativity in implementing gaze tracking for yourself.

- [Understanding Gaze Tracking Demo](#understanding-gaze-tracking-demo)
- [Put That, There Demo](#put-that-there-demo)
- [Simon Game Demo](#simon-game-demo)

### Understanding Gaze Tracking Demo

This first example is fundamentally a proof of concept that helped me better understand the nature of gaze data within Vuforia Studio. Beacause it was the first AR experience created that incorperates gaze tracking, it is primarily focused on making gaze tracking data visible. There are six on-screen labels that constantly update with the user's X, Y, & Z-coordinates (the yellow point in the above explanation), as well as the X, Y, & Z components of the gaze vector (the blue vector in the above explanation). This data display allows the user to see the gaze data that are being processed in real time and gives them a better idea of what the data actually look like.

In addition to the data display, there is a basic example of moving a model within a 3D space based on the user's position. There is a small model of the Death Star that mirrors the user's position across the X-Y plane that moves left, right, up, or down with the user's device just like an object in a real mirror would. A brief screen recording of this AR experience is included below:

*As the user moves left and right, up and down, or forward and backward, watch the X, Y, and Z labels change, respectively.*

[![Understanding Gaze Tracking Demo Video](https://img.youtube.com/vi/XZiJFjOexxo/0.jpg)](https://www.youtube.com/watch?v=XZiJFjOexxo)

The "Understanding Gaze Tracking Demo" experience can be downloaded [here](AR%20Experience%20Files/Understanding_Gaze_Tracking_Demo.zip) or viewed with the [ThingMark](#thingmark-for-viewing-ar-experiences) above.

### Put That, There Demo

The next example shows how gaze tracking can be used to move entire models within an AR experience. Currently, Vuforia Studio lacks the ability to reposition individual models without moving the tracking for the entire experience. This means that it is presently impossible to move AR objects relative to each other, which would necessary for tasks like laying out a space (e.g., a shop floor) using augmented reality. This AR experience serves as a remedy to this inability and is a powerful demonstration of how gaze tracking could be used to manipulate objects within an AR experience. It is based on a retro MIT Architecture Machine Group demo [Put That There](https://youtu.be/CbIn8p4_4CQ).

The mechanism for this experience is as follows: A voice command (HoloLens) or a on-screen button (mobile devices) is used to trigger the model relocation. The model displaying on the user's screen is selected and the relocation process begins. (If there is more than one model on screen, the model closest to the user is selected.) The selected model's position is determined by the point at which the user's gaze vector (the blue vector in the above explanation) intersects the ground plane (Y=0). This intersection provides an X-Z coordinate for the model to follow and once the desired position is found, the model can be locked in place with another voice command or button-press. A brief screen recording of this AR experience is included below:

*Models within the AR experience are moved relative to each other throughout the 3D environment using a Microsoft HoloLens 2.*

[![Put That, There on HoloLens 2](https://img.youtube.com/vi/h0_2xMTR_lk/0.jpg)](https://www.youtube.com/watch?v=h0_2xMTR_lk)

*Additionally, an updated twin of the AR experience can be rendered in Onshape.*

[![Put That, There with Onshape Twin](https://img.youtube.com/vi/_Gu3hrTNyVs/0.jpg)](https://www.youtube.com/watch?v=_Gu3hrTNyVs)

The "Put That, There Demo" experiences can be downloaded [here](https://github.com/PTC-Education/Gaze-Tracking-Demos/raw/main/AR%20Experience%20Files/Put_That__There_Demo.zip) for mobile devices or [here](AR%20Experience%20Files/Put_That__There_Demo_-_HoloLens.zip) for 3D Eyeware, or viewed with the [ThingMark](#thingmark-for-viewing-ar-experiences) above.

### Simon Game Demo

The last example in the object manipulation category demonstrates how gaze tracking can be used to interact with specific components on a model. In contrast to the "Put That, There" Demo that focuses on moving an entire model, this AR experience is lets users select specific part of a model using their gaze. This is done by tracking the user's gaze in relation to a specified portion of the model, rather than the model in its entirety. The ability to identify certain parts of a model greatly enhances the capabilities of gaze tracking and creates many additional applications in which gaze tracking could be used.

This AR experience is an augmented reality recreation of the classic game "[Simon"](https://en.wikipedia.org/wiki/Simon_(game)) and can be played either by gaze or by touch. When playing by gaze, the user selects the game's buttons using their gaze vector (the blue vector in the above explanation). The vector's position is represented by an on-screen reticle to make selecting easier. When selected, the button in question is highlighted, then pressed after a brief delay. When playing by touch, the user selects the game's button simply by pressing on their device screen, much like what happens in the physical game. A brief screen recording of this AR experience is included below:

*The classic game "Simon" is now in augmented reality and can be played either by gaze or by touch.*

(Screen recording of Simon game)

The "Simon Game Demo" experience can be downloaded [here] or viewed with the [ThingMark](#thingmark-for-viewing-ar-experiences) above.

## Analytical Applications

The other potential use case for gaze tracking detailed here is harvesting and logging data about the user's gaze in order to perform analysis and learn more about the users themselves. This analysis could be very useful to AR authors seeking quantitative feedback because they could see exactly how users move through their AR experiences and/or what they were looking at. It could also help those managing AR experiences (e.g., educators or line managers in a factory) to monitor how their users are interacting with the AR experiences. Listed below are some simple demos to show potential use cases and inspire your creativity in implementing gaze tracking for yourself.

- [Quantifying Gaze Duration Demo](#quantifying-gaze-duration-demo)
- [Board of Colorful Labels Demo](#board-of-colorful-labels-demo)
- [Ring of Colorful Labels Demo](#ring-of-colorful-labels-demo)
- [Other Ideas for Analytics](#other-ideas-for-analytics)

### Quantifying Gaze Duration Demo

The first example in the analytics category was created as a testing grounds to figure out how to quantify the time spent looking at each object in the AR experience. It is similar to the "Understanding Gaze Tracking Demo" above, in that it is primarily focused on making gaze tracking data visible. There are seven on-screen labels that constantly update with the total time spent in the AR experience, the user's focus on both objects, their distance from both objects, as well as the time they have spent looking at each object. This data display allows the user to see the gaze data that are being processed in real time and gives them a better idea of what the data actually look like.

This experience is able to determine if a user is looking at an object by taking the dot product between the gaze vector (the blue vector in the above explanation) and the vector from the user to the object in question. When used with unit vectors, the dot product yields a value between \[-1, 1\] and the closer the result is to 1, the closer the two vectors are aligned. Testing was performed to determine that a dot product was greater than or equal to 0.85 meant the object was currently displayed on the screen. It could then be concluded that when the dot product of the gaze vector and any object exceeded the threshold of 0.85, the gaze timer for that object should increment. A brief screen recording of this AR experience is included below:

*As the user focuses their gaze on each object, the corresponding timer increments to compute the total gaze duration for that object.*

[![Quantifying Gaze Duration Demo Video](https://img.youtube.com/vi/N58wQ4ZVTQk/0.jpg)](https://www.youtube.com/watch?v=N58wQ4ZVTQk)

The "Quantifying Gaze Duration Demo" experience can be downloaded [here](AR%20Experience%20Files/Quantifying_Gaze_Duration_Demo.zip) or viewed with the [ThingMark](#thingmark-for-viewing-ar-experiences) above.

### Board of Colorful Labels Demo

The next example shows how gaze tracking can be used to conduct experiments to quantify how captivated users are by different elements within the AR space. This AR experience contains 10 3D labels that all different colors and strives to quantify how different colored labels engage the user's attention. The color of the each label is randomly assigned each time the experience is opened in order to minimize any bias created by the label's position. The labels have been arranged like a flat billboard for easy viewing.

As the user moves throughout the AR experience, their gaze data is continuously passed into ThingWorx and logged in a DataTable to be analyzed later. This data table contains fields for 

[![Board of Colorful Labels Demo Video](https://img.youtube.com/vi/QF1vHx24uEY/0.jpg)](https://www.youtube.com/watch?v=QF1vHx24uEY)

The "Board of Colorful Labels Demo" experience can be downloaded [here] or viewed with the [ThingMark](#thingmark-for-viewing-ar-experiences) above.

### Ring of Colorful Labels Demo

Basically a repeat of the "Board of Colorful Labels Demo", but with a different layout for the labels.

The "Ring of Colorful Labels Demo" experience can be downloaded [here] or viewed with the [ThingMark](#thingmark-for-viewing-ar-experiences) above.

### Other Ideas for Analytics

Propose applications with heat maps of both where the user is looking and where they moved in the 3D space. Find some way to show how user's location changes over time.
