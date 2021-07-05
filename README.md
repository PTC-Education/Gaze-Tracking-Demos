# Gaze-Tracking
**Purpose:** To inspire creativity in others to find meaningful applications for gaze tracking.

**Summary:** A conglomeration of AR experiences that showcase the power of gaze tracking. The experiences herein can be classified into two primary groups,  proofs of concept or analytical applications. Each experience highlights a separate use case and is intended to inspire creators think about how gaze tracking could enhance their own AR experiences.

### **Table of Contents**

- [What is Gaze Tracking?](#what-is-gaze-tracking)
- [Proofs of Concept](#proofs-of-concept)
  - [Basic Model Manipulation Demo](#basic-model-manipulation-demo)
  - Timing Gaze Duration Demo
  - Put That, There Demo
- Analytical Applications
  - Field of Colored Labels #1
  - Field of Colored Labels #2

## What is Gaze Tracking?

### Background Explanation

Before we jump right into an explanation of gaze tracking, it is important that you understand a little bit about how the position and orientation of objects are defined in a virtual 3D space. To start off, virtually positioning an object in a 3D environment isn't something that was invented for augmented reality. It has actually been around much longer and is widely used in almost every video game you have ever played. It is what allows the computer to keep track of your character and the other objects in the environment and is crucial as you move throughout the virtual area.

In order to define an object's position, the computer must know the object's location and which way it is facing. The location data typically come in the form of 3-dimensional coordinates *(X,Y,Z)*, while the orientation data are commonly a set of orthogonal vectors or angles. These data fully-define any object in 3D space and are essential for a realistic rendering of the virtual environment.

### Position & Orientation in Vuforia 

Vuforia Engine defines objects within the augmented reality space using this same convention. Every object that is placed into the AR environment has X, Y, & Z-coordinates, as well as X, Y, & Z-rotations 
