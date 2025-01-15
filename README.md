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
 

 
