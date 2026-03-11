
# Real-Time Object Detection with SSD MobileNet

This repository contains a Python-based real-time object detection system. It utilizes OpenCV's Deep Learning module (dnn) and a pre-trained SSD (Single Shot MultiBox Detector) MobileNet V3 model to identify and label objects from image files or live video feeds.

## Overview

The project leverages the COCO (Common Objects in Context) dataset parameters to recognize 80 different classes of everyday objects. By using the MobileNet V3 backbone, the system is optimized for high-speed performance, making it suitable for hardware with limited computational power.

## Key Features

* **Real-Time Performance:** Uses SSD MobileNet V3 for a balance between speed and accuracy.
* **Multi-Class Detection:** Capable of identifying up to 80 distinct object categories defined in the COCO dataset.
* **Flexible Input:** Supports object detection on static images (as seen in `code1.py`) and real-time video streams (as seen in `code2.py`).
* **Automated Labeling:** Draws bounding boxes and applies class labels with confidence scores directly onto the visual output.

## Repository Structure

* `code1.py`: Script for object detection on static images.
* `code2.py`: Script for real-time object detection via webcam.
* `frozen_inference_graph.pb`: The pre-trained weights of the SSD MobileNet model.
* `ssd_mobilenet_v3_large_coco_2020_01_14.pbtxt`: The configuration file for the model architecture.
* `coco.names`: A text file containing the names of the 80 object classes.
* `lena.png`: A sample image used for testing the detection scripts.

## Prerequisites

Ensure you have Python 3.x installed. You will need the `opencv-python` library to run the scripts.

```bash
pip install opencv-python

```

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/Adarsh-Aravind/image_classification.git
cd image_classification

```

### 2. Run Image Detection

To test the detection on a static image file:

```bash
python code1.py

```

### 3. Run Real-Time Detection

To launch the object detection system using your system's default camera:

```bash
python code2.py

```

## How It Works

1. **Model Loading:** The script loads the `.pb` (weights) and `.pbtxt` (config) files into OpenCV’s `dnn_DetectionModel`.
2. **Preprocessing:** Input frames are resized to 320x320, and pixel values are scaled to meet the requirements of the MobileNet architecture.
3. **Inference:** The model processes the frame and returns class IDs, confidence scores, and bounding box coordinates.
4. **Visualization:** OpenCV functions draw the results onto the frame, filtering out detections below a specified confidence threshold (default is 50%).

## Acknowledgments

* Powered by [OpenCV](https://opencv.org/).
* Model weights and configuration based on the [TensorFlow Detection Model Zoo](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/tf2_detection_zoo.md).

---

### Suggested GitHub Topics

`object-detection` `opencv` `python` `mobilenet-ssd` `computer-vision` `real-time` `machine-learning` `coco-dataset`