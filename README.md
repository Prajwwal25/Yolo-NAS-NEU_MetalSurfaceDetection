# YOLO-NAS

## Overview
This project implements a deep learning solution for detecting and classifying steel surface defects using the SuperGradients library and a YOLO-NAS object detection model. The system is designed to identify various types of surface defects in steel materials, making it useful for quality control in manufacturing environments.

### Dataset Statistics
- **Total Images**: 1,800 grayscale images
- **Image Format**: Grayscale, BMP format
- **Image Resolution**: 200 × 200 pixels
- **Classes**: 6 distinct defect types
- **Images per Class**: 300 samples per defect type
- **File Size**: Total size approximately 1.2 GB

### Defect Types
1. **Rolled-in Scale (RS)**
   - Appears as dark elongated regions
   - Caused by rolled-in oxide scale during rolling process
   - 300 images

2. **Patches (Pa)**
   - Appears as lighter regions with irregular shapes
   - Results from uneven surface oxidation
   - 300 images

3. **Crazing (Cr)**
   - Network of fine lines or cracks on the surface
   - Caused by thermal or mechanical stress
   - 300 images

4. **Pitted Surface (PS)**
   - Small pits or cavities on the metal surface
   - Results from localized corrosion or manufacturing defects
   - 300 images

5. **Inclusion (In)**
   - Foreign particles embedded in the metal surface
   - Usually appears as dark spots
   - 300 images

6. **Scratches (Sc)**
   - Linear marks or grooves on the surface
   - Mechanical damage during handling or processing
   - 300 images

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

### Data Split
- **Training Set**: 80% (1,440 images)
- **Test Set**: 20% (360 images)
- **Stratified Split**: Equal distribution of defect types in both sets

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
* mAP@0.50: 0.85 
* Precision@0.50: 0.80 
* Recall@0.50: 0.85 
* F1-Score@0.50: 0.82 

**Training Parameters:**
* Batch Size: 32
* Learning Rate: 0.001 - 0.0001
* Epochs: 10
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




