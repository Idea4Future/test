
# ROSBag Data Download and Conversion Guide

## Download Data File (ROSBag)

[Download Link](https://www.uma.es/robotics-and-mechatronics/info/132852/negs-ugv-dataset?set_language=en)

By following this link, you can download a ZIP file (containing human-readable text format and JPEG images) and a ROSBAG ZIP file.

### ZIP FILE (human-readable text format and JPEG images):
- Contains RGB images, segmentation image data, and other related data.

### ROSBAG:
- Originally developed for ROS1. After converting it to ROS2, you can monitor the topics in real-time.

> **Note:** When running this ROS bag, RGB images are published as `/CompressedImage`. To visualize these images in RViz, you must convert the `/CompressedImage` messages into standard `/Image` messages.

---

## How to Convert ROS1 ROSbag to ROS2

### 1. Install the `rosbags` Library

Open a terminal and run the following command:

```bash
pip install rosbags
```

### 2. Navigate to Your ROSbag File Location

Move to the directory containing your ROS1 `.bag` file:

```bash
cd /path/to/your/rosbag
```

### 3. Convert ROS1 Rosbag to ROS2

Run the `rosbags-convert` command to convert your `.bag` file to ROS2 format. Replace `your_rosbag_file.bag` with your file's name:

```bash
rosbags-convert --src your_rosbag_file.bag --dst output_ros2_bag
```

### 4. Play the Converted ROS2 Bag

Once converted, play the ROS2 bag with:

```bash
ros2 bag play output_ros2_bag
```
