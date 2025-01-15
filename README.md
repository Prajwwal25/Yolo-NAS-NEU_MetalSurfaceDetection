# Yolo-NAS-NEU_MetalSurfaceDetection
#### This project utilizes the YOLO model for detecting defects on steel surfaces. It is implemented using the super-gradients library and involves training, evaluating, and visualizing results to achieve high detection accuracy


## Features 
 ###### Dataset Statistics: 1,800 grayscale images
 ###### Resolution: 200 × 200 pixels
 ###### Number of Defect Categories: 6
 ###### Images per Category: 300

### Defect Categories
 ###### Rolled-in Scale (RS): Appears as dark elongated patches
 ###### Patches (Pa): Surface breaking with localized corrosion
 ###### Crazing (Cr): Interconnected surface breaking
 ###### Pitted Surface (PS): Irregular pits or cavities on the surface
 ###### Inclusion (In): Embedded foreign materials
 ###### Scratches (Sc): Linear surface marks or indentations

### Dataset Structure
 
NEU Metal Surface Defects/
├── train/
│   ├── Crazing/
│   ├── Inclusion/
│   ├── Patches/
│   ├── Pitted_Surface/
│   ├── Rolled-in_Scale/
│   └── Scratches/
├── valid/
│   └── [same structure as train]
└── test/
    └── [same structure as train]






 ### Data Split
  ##### Training Set: 1,656 images
  ##### Validation Set: 72 images
  ##### Test Set: 72 images

###  Model : YOLOv3 implementation for object detection.



### Metrics: Evaluation using mAP@0.5, Precision, and Recall.



### Visualization: Bounding boxes on test images.


## Requirements

 ##### Python 3.7+
 ##### Super Gradients Library
 ##### PyTorch
 ##### Additional dependencies in requirements.txt

##### Install dependencies:
 ### pip install -r requirements.txt


## Metrics Displayed
 #### mAP@0.5: Mean Average Precision at IoU threshold 0.5.
 #### Precision: Ratio of true positives to all predicted positives.
 #### Recall: Ratio of true positives to all ground truth objects.

## Example Output
 ### Validation Results:
 #### mAP@0.5: 0.85
 #### Precision: 0.82
 #### Recall: 0.78

## Visualization

  ![image](https://github.com/user-attachments/assets/5c10ffee-72e8-49b9-a065-6615a3d0871a)


 
 






 

 
