# Visual-Inertial Odometry

This repository implements a Visual-Inertial Odometry (VIO) system for autonomous drone navigation.

## Overview

The goal of this project is to estimate the pose (position and orientation) of an autonomous drone using sequential camera frames. The approach combines deep learning techniques:

1. **Feature Extraction with CNN**: A convolutional neural network extracts visual features from input frames
2. **Pose Regression with LSTM**: The extracted features are fed into LSTM networks to learn temporal dependencies across sequential frames and regress the drone's pose

## Technical Details

### Framework
- **PyTorch** for deep learning model implementation

### Architecture
- **CNN Backbone**: Extracts spatial features from individual camera frames
- **LSTM Network**: Processes sequences of CNN features to capture temporal dynamics and motion patterns

### Pose Representation
The drone pose is represented as a 7-dimensional vector:
- **Position**: `(tx, ty, tz)` - 3D translation coordinates
- **Orientation**: `(qx, qy, qz, qw)` - quaternion representation for rotation

### Input Data
- Stereo camera images (left camera) captured during drone flight
- Ground truth poses with timestamps for supervised training

## Dataset

The dataset used for this project is from the [UZH-FPV Drone Racing Dataset](https://fpv.ifi.uzh.ch/datasets/).

The ground truth data follows the format:
```
timestamp tx ty tz qx qy qz qw
```  
