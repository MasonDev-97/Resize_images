# Dog and Cat Classification via Webcam Using YOLOv8

## Introduction

This project utilizes YOLOv8 to train and deploy an AI model capable of distinguishing between dogs and cats through a webcam or image input. The goal is to create a simple application that can accurately identify pets in real-time.

---

## Table of Contents

1. [What is YOLOv8?](#what-is-yolov8)
2. [Uses of YOLOv8](#uses-of-yolov8)
3. [How YOLOv8 Works](#how-yolov8-works)
4. [Installation and Setup](#installation-and-setup)
5. [Usage Guide](#usage-guide)
6. [Contributing](#contributing)

---

### What is YOLOv8?

YOLOv8 (You Only Look Once, version 8) is one of the latest models in the field of object detection. Designed for high-speed and high-accuracy image recognition and classification, YOLOv8 leverages deep learning techniques to detect specific objects within images or videos in real-time.

YOLOv8 features significant improvements in network architecture and algorithm optimization compared to previous YOLO versions, allowing for reduced computation time and increased accuracy. This makes it an excellent choice for high-performance applications and easy deployment.

### Uses of YOLOv8

YOLOv8 is widely applied in fields such as:

- **Security Surveillance**: Recognizing and tracking human movements and detecting dangerous objects.
- **Autonomous Vehicles**: Assisting vehicles in detecting objects, road signs, pedestrians, and other vehicles.
- **Healthcare**: Identifying abnormalities in medical imaging.
- **Pet Identification**: In this project, YOLOv8 will be used to distinguish between dogs and cats based on images or videos.

### How YOLOv8 Works

YOLOv8 is a convolutional neural network (CNN) trained to detect and classify objects in real-time. The model "looks" at the image only once, dividing it into a grid and predicting bounding boxes and probabilities for objects within each grid cell.

Basic steps include:

1. **Dividing the image into grid cells**: The input image is divided into a grid.
2. **Object detection**: Each grid cell predicts bounding boxes and the probability of objects within them.
3. **Non-max suppression (NMS)**: Overlapping boxes are removed, keeping only the highest-confidence boxes.

YOLOv8 can run on both CPU and GPU, but for optimal speed and performance, using a GPU is recommended.

---

## Installation and Setup

### Software Requirements

- Python 3.8 or later
- pip (Python package manager)
- CUDA (if you plan to run YOLOv8 on a GPU)

### Installation Guide

1. **Install Python and pip** (if not already installed).
2. **Install Ultralytics YOLOv8**:
   ```bash
   pip install ultralytics
   ```

3. **Clone this project**:
   ```bash
   git clone https://github.com/yourusername/dog-cat-detector.git
   cd dog-cat-detector
   ```

4. **Install other required libraries**:
   ```bash
   pip install -r requirements.txt
   ```

---

## Usage Guide

### 1. Train the Model
   First, you'll need a dataset of images containing dogs and cats with corresponding labels. Once you have the dataset, use the following command to start training the model:

   ```python
   from ultralytics import YOLO

   model = YOLO("yolov8n.pt")  # Load the base YOLOv8 model
   model.train(data="data/dog_cat.yaml", epochs=50)  # Train the model with custom dataset
   ```

   - `data/dog_cat.yaml` is a dataset configuration file that includes paths to dog and cat images and their labels.

### 2. Real-time Detection via Webcam
   To detect dogs and cats in real-time using a webcam, use the following code:

   ```python
   model.predict(source=0, show=True)  # `source=0` opens the webcam
   ```

   Running this command will open your webcam and display bounding boxes around detected dog or cat objects.

### 3. Detection on Images
   If you want to detect dogs and cats in a specific image, replace `source=0` with the image path:

   ```python
   model.predict(source="path/to/image.jpg", show=True)
   ```

---

## Contributing

This project is open for contributions! If you encounter any issues or would like to add new features, please open an `Issue` or create a `Pull Request`. We welcome all suggestions and contributions!

---

We hope this project helps you understand YOLOv8 and how to implement it to create a real-time system that distinguishes between dogs and cats!