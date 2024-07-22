# nasa-micro-g-next
## Overview
The Search & Emergency Equipment for Life-saving Identification & Optical Network (SEE LION) is an autonomous camera system designed for the NASA Micro-gravity Neutral Buoyancy Experiment Design Team (Micro-g NExT). The SEE LION uses the You-Only-Look-Once (YOLOv8) object detection algorithm to autonomously identify and track target items indicating the presence of astronaut crew members to be rescued during emergency water landings of the Orion capsule in the Artemis program. These items of interest are:  
* Class 1: Orange-colored life ring  
* Class 2: Mannequin wearing orange-colored life preserver unit (LPU)  
* Class 3: Multi-person life raft  
* Class 4: Orion capsule mockup (WEST) located at the far end of the pool

## Prerequisites
* ultralytics
* cv2
* torch
* PIL
* tkinter
* customtkinter
* time

## Usage
To use the SEE LION, install the above dependencies and download the custom-trained YOLOv8 weights file that performed the best during training and validation ('**best.pt**') and the SEE LION graphic user interface ('**seelionGUI**'). Modify the line in the SEE LION graphic user interface below to point to the custom-trained YOLOv8 weights file:  

```model = YOLO('C:/Users/Gigabyte/Downloads/nasa-micro-g-next/best.pt')```  

Change the confidence threshold in the line in the SEE LION graphic user interface below: 
 
```results = model(frame, conf=0.3)```  

Alternatively, download '**last.pt**' instead of '**best.pt**' to use the last custom-trained YOLOv8 weights file.  

## Contents  
* best.pt: Custom-trained YOLOv8 weights file that performed the best during training and validation
* last.pt: Last custom-trained YOLOv8 weights file
* seelionGUI.py: SEE LION graphic user interface
* yolov8.ipynb: Google Colab file used to custom-train YOLOv8 algorithm
* dataset
  * train: 277 images and labels used for training (70% of total dataset)
  * valid: 79 images and labels used for validation (20% of total dataset)
  * test: 38 images and labels used for testing (10% of total dataset)
  * data.yaml
* detect
  * train: Training results
  * valid: Validation results
* F1_curve.png: F1 curve of custom-trained YOLOv8 weights
* PR_curve.png: Precision-recall curve of custom-trained YOLOv8 weights
* P_curve.png: Precision curve of custom-trained YOLOv8 weights
* R_curve.png: Recall curve of custom-trained YOLOv8 weights
* confusion_matrix.png: Confusion matrix of custom-trained YOLOv8 weights based on 83 unseen images and labels
* saved_frame_2024-07-14 14-50-00.png: Example of screenshot from SEE LION graphic user interface in saved_frame_YYYY-MM-DD hh-mm-ss.png format
* IMG_7548.mp4: Example of live inference applying custom-trained YOLOv8 weights
* deliverables
  * fy24-micro-g-next-challenge-description.pdf: 2024 NASA Micro-g NExT challenge description
  * 2024 SEE LION Proposal.pdf: SEE LION proposal from Columbia Space Initiative Micro-g team
  * Columbia Space Initiative_Columbia University Proposal Feedback.pdf: Micro-g NExT proposal feedback from NASA
  * Award Letter Template_ AL-51405.pdf: NASA offer letter
