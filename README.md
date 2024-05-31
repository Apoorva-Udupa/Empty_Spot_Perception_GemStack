# Empty Spot Perception with GEMStack

This repository is part of an advanced Automatic Parking Project, focusing specifically on Empty Parking Spot Perception within GEMStack. Leveraging a custom dataset and the powerful YOLOv8 algorithm, this implementation accurately detects empty parking spots with high precision.

## Table of Contents

- [Overview](#overview)
- [Dataset](#dataset)
- [Training and Validation](#training-and-validation)
- [Performance](#performance)
- [How to Use](#how-to-use)

## Overview

The Empty Spot Perception module aims to enhance automatic parking systems by precisely identifying empty parking spots through oriented bounding boxes (OBB). Utilizing a meticulously curated dataset and the YOLOv8 model, this project achieves exceptional accuracy in diverse environments.

## Dataset

### Custom Training Dataset

A comprehensive dataset has been constructed, featuring images of empty parking lots accompanied by label files (.txt) detailing the positions of annotated bounding boxes in the format (x, y, w, h, r). Tools like Makesense.ai and Roboflow facilitated the generation of these labels.

- **(x, y)**: Center of the bounding box within the image
- **(w, h)**: Width and height of the bounding box
- **(r)**: Rotation angle of the bounding box

#### Dataset Composition

| Image Type       | No. of Images | No. of Labels |
|------------------|---------------|---------------|
| Carla Simulation | 175           | 120           |
| Twilight         | 47            | 34            |
| Real-time        | 90            | 80            |
| Test-site (rosbags) | 150         | 110           |

## Training and Validation

The dataset was divided into 95% for training, 4% for validation, and 2% for testing. The YOLOv8 OBB model was trained to achieve a mean Average Precision (mAP) of 92%.

### Training Parameters

- **Epochs**: {50, 70, 80, 100}
- **Batch size**: {5, 7, 10}
- **Confidence score**: > 0.7
- Both single image and real-time video stream processing (via webcam) were tested using rosbags.

The model reliably detected bounding boxes, providing accurate spatial representations in various images.

## Performance

The YOLOv8 OBB model demonstrated outstanding performance, achieving a high mAP and excelling in both single image and real-time video stream tests. Its robustness and reliability were consistently validated across different scenarios.

## How to Use

To deploy this model for detecting empty parking spots, follow these instructions:

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/Apoorva-Udupa/Empty_Spot_Perception_GemStack.git
   cd Empty_Spot_Perception_GemStack
