Kinect Depth and Color Frame Viewer
This project is a basic C++ application that interfaces with a Kinect sensor to acquire depth and color frames, map the depth data to the color space, and visualize the result. It demonstrates Kinect sensor initialization, frame reading, coordinate mapping, and buffer management.

Features
Initializes Kinect v2 sensor and required frame readers.

Captures depth and color frames.

Maps depth data to color space using the coordinate mapper.

Visualizes mapped color data for each depth pixel.

Manages memory and resource cleanup gracefully.

Dependencies
Kinect for Windows SDK 2.0

C++11 or later

Windows platform

File Overview
app.h
Header file for the App class (not included here but expected to contain declarations for methods like Init, Tick, and Shutdown, as well as necessary member variables).

app.cpp
Main implementation of the App class:

Init(): Initializes the Kinect sensor, sets up readers for depth and color streams, and allocates memory buffers.

Tick(float deltaTime): Called every frame to:

Acquire the latest depth and color frames.

Map depth pixels to corresponding color pixels.

Populate a visual buffer for rendering.

Shutdown(): Releases resources and deallocates memory.

Usage
Build the Project

Make sure the Kinect SDK is installed and the library paths are configured in your project.

Build using Visual Studio or a compatible C++ toolchain.

Run the App

Connect a Kinect v2 sensor.

Run the application. It will print log messages and handle frame copying each frame.

Notes
Frame resolution is hardcoded (1920x1080 for color, variable for depth depending on Kinect spec).

Depth data is visually replaced with the corresponding color data where valid, and colored red where mapping is invalid.

Includes minimal error handling and diagnostic printing.

License
This project is for educational or prototyping use. No formal license is provided.

