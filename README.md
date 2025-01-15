# Steel Surface Defect Detection using SuperGradients and YOLO-NAS

## Overview
This project implements a deep learning solution for detecting and classifying steel surface defects using the SuperGradients library and a YOLO-NAS object detection model. The system is designed to identify various types of surface defects in steel materials, making it useful for quality control in manufacturing environments.

## Features
* **Real-time Detection**: YOLO-NAS object detection framework for fast inference
* **Transfer Learning**: Pre-trained COCO weights for efficient model development
* **Custom Classification**: Tailored for steel surface defect identification
* **Data Enhancement**: Comprehensive augmentation pipeline
* **Performance Monitoring**: Detailed training and evaluation metrics

## Installation

### Hardware Requirements
* Minimum 8GB RAM
* GPU support recommended for faster training

### Software Dependencies
```bash
python
super-gradients
torch
numpy
matplotlib
PIL
```

## Dataset Structure
Your dataset should be organized as follows:
```plaintext
steel_defect_dataset/
├── train/
│   ├── images/
│   │   ├── image1.jpg
│   │   ├── image2.jpg
│   │   └── ...
│   └── labels/
│       ├── image1.txt (YOLO format)
│       ├── image2.txt (YOLO format)
│       └── ...
└── test/
    ├── images/
    │   ├── image1.jpg
    │   ├── image2.jpg
    │   └── ...
    └── labels/
        ├── image1.txt (YOLO format)
        ├── image2.txt (YOLO format)
        └── ...
```

## Implementation

### Model Architecture
Create a model configuration file (`model.yaml`):

```yaml
name: yolo_nas_l  # Model name
pretrained: coco  # Pre-trained weights
num_classes: 6    # Number of defect classes
train_dir: ./data/train
val_dir: ./data/val
batch_size: 16
epochs: 100
```

### Training Process
1. Set up your dataset following the structure above
2. Configure your `model.yaml` file
3. Run training:

```bash
sg train configs/model.yaml
```

### Model Performance
**Training Metrics:**
* mAP@0.50: 0.85 - 0.92
* Precision@0.50: 0.80 - 0.90
* Recall@0.50: 0.85 - 0.95
* F1-Score@0.50: 0.82 - 0.92

**Training Parameters:**
* Batch Size: 16-32
* Learning Rate: 0.001 - 0.0001
* Epochs: 100-200
* Optimizer: AdamW
* Data Augmentation: Random flips, rotations, crops, color jittering

## Usage

### Making Predictions
```python
from super_gradients.inference import Model

# Load the trained model
model = Model.load("path/to/checkpoint")

# Load an image
image = cv2.imread("new_image.jpg")

# Make prediction
predictions = model.predict(image)

# Process and visualize predictions
```




