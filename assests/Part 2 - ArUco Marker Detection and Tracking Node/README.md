# ArUco Tracking Solo Mission

This ROS2 package detects ArUco markers from a camera feed using OpenCV and publishes their 3D poses and IDs as a `MarkerArray` that can be directly visualized in RViz.

**Note:** This solution uses **only camera data** and OpenCV for pose estimation. **No LiDAR** or external sensors are required or used.

## Configuration for Simulation Environment

If you are setting up a simulation environment for this node, please place your ArUco markers according to these default parameters:

- **Marker Dictionary**: OpenCV ArUco Dictionary ID `7` (e.g., `DICT_5X5_1000`)
- **Marker Size**: `0.15` meters (15 cm)


## Prerequisites & Dependencies

Ensure you have the following installed:
- ROS2 (Humble/Iron/Jazzy depending on your setup)
- OpenCV and `cv_bridge`

To ensure absolutely no missing dependencies on your machine, it is highly recommended to run `rosdep` from the root of your workspace before building:

```bash
cd <your_workspace> # e.g. cd ~/asuroar/aruco_solo_mission
rosdep install --from-paths . --ignore-src -r -y
```

## Build Instructions

To build the workspace, run the following commands from the root of your workspace:

```bash
cd <your_workspace> # e.g. cd ~/asuroar/aruco_solo_mission
colcon build --packages-select aruco_tracking
source install/setup.bash
```

## Run Instructions

You can run the node using the following command:

```bash
ros2 run aruco_tracking aruco_node
```

### Parameters
- `arucoDictType` (int, default: `7`): The OpenCV ArUco dictionary ID.
- `markerSize` (float, default: `0.15`): The physical size of the printed ArUco marker in meters.

## Topics

### Subscribed Topics (Inputs)
- **`/image_raw`** (`sensor_msgs/msg/Image`): Publish your raw simulated camera images here.
- **`/camera/color/camera_info`** (`sensor_msgs/msg/CameraInfo`): **(Highly Recommended)** Publish your simulated camera's intrinsic parameters here perfectly synced with the image. The node uses this for highly accurate 3D pose estimation. If not provided, it falls back to a hardcoded standard matrix.

### Published Topics (Outputs)
- **`/aruco_markers`** (`visualization_msgs/msg/MarkerArray`): Subscribe to this topic in **RViz**! Add a `MarkerArray` display and set the topic to `/aruco_markers`. You will see green 3D cubes representing the estimated poses of the markers, along with floating white text showing each marker's ID. 
  *(Ensure your RViz fixed frame is set to the camera's frame, e.g., `camera_link` or the frame ID from the image header).*
- **`/perception/detected_aruco`** (`vision_msgs/msg/Detection2DArray`): Provides 2D bounding boxes and IDs of the detections.
