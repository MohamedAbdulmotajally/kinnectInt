# Kinect Frame Mapping Application

This project is a simple C++ application that interfaces with a Kinect v2 sensor to acquire depth and color frames, map depth data to the color space, and visualize it. The application initializes the Kinect, reads frame data, processes it, and handles cleanup.

## Features

- Initializes Kinect v2 sensor.
- Reads and processes depth and color frames.
- Maps depth data to the corresponding color pixels.
- Simple buffer-based visualization.
- Error handling with debug print statements.

## Requirements

- **Windows OS**
- **Kinect for Windows SDK v2.0**
- **C++11 or later**
- Visual Studio (or another Windows C++ compiler)

## Code Overview

### `App::Init()`
Initializes the Kinect sensor and sets up the necessary frame readers and buffers:

- Connects to the default Kinect sensor.
- Retrieves depth and color frame sources and readers.
- Allocates memory for depth, color, and mapped pixel buffers.
- Gets a coordinate mapper to transform depth to color space.

### `App::Tick(float deltaTime)`
Main update loop (called per frame):

- Acquires the latest depth and color frames.
- Copies frame data into local buffers.
- Maps each depth point to its corresponding color space point.
- Populates a display buffer, coloring invalid points red.

### `App::Shutdown()`
Cleans up all allocated resources:

- Releases readers and sensor handles.
- Frees dynamically allocated buffers.

## How to Build

1. Install **Kinect for Windows SDK v2.0**.
2. Open the project in Visual Studio.
3. Link against Kinect20.lib and include the SDK headers.
4. Compile and run with Kinect connected.

## Example Output

During execution, console output will indicate frame capture progress:

