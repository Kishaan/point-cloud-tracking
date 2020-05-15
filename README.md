# software-development-project

Preliminary tracking for pointcloud data of objects on a rotating table. 

## Project: 3D object detection and tracking

The Rotating-Table-Test (RTT) in the RoboCup@Work competition requires the detection, tracking and recognition of objects moving on a rotating table. An existing scene segmentation component segments objects lying on a planar surface using 3D pointclouds. In order to use this component for RTT, some refactoring and new functionalities are required.

## Problem Statement

* In its current set up, it is not programmed for dynamic scenes (i.e. it performs a one-shot segmentation on a static scene).
* Needs some functionality for tracking the objects.
* Needs a functionality that can exploit the circular motion of the objects on the table.
* No functionalities to estimate speed and motion path of the segmented objects.

### Goals Achieved

* Refactored code to account for the dynamic scene. In particular, the plane needs to be extracted just once, while multiple segmentation and clustering operations can be performed using the once extracted plane.
* Functionality added to track the objects based on a naive nearest-neighbor algorithm.
* Estimated a circle for each object to calculate the speed of rotation and position of object at a given time.