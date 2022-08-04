# YOLOv5m training using finetuning and data augmentation on a custom labeled dataset

Object detection YOLOv5m finetuning on custom dataset with PyTorch. The custom dataset was labeled in CVAT and preprocessed in Roboflow. Data augmentation is implemented in the last experiments. Inference on images.

Original YOLOv5 repository:
https://github.com/ultralytics/yolov5

## Directory Structure

**All the code files and folders follow the following structure.**

```
├── data.yaml
├── README.dataset.txt
├── README.roboflow.txt
├── inference
├── test
│   ├── images
│   └── labels
├── train
│   ├── images
│   └── labels
└── yolov5
```

## Introduction

It is used YOLOv5m model, which has been trained on the MS COCO dataset. In the notebook provided, the model is finetuned on a custom dataset using PyTorch. 

Is it used a <a href="https://app.roboflow.com/ds/ReliRzR2PO?key=INYILG4hU7" target="_blank">Dataset of fruits</a> that was previouly labeled in CVAT and preprocessed in Roboflow. It consists of 300 images with apples, bananas and oranges labelled. This dataset will be used for training the custom YOLOv5 object detector. Original dataset is located in <a href="https://www.kaggle.com/datasets/mbkinaci/fruit-images-for-object-detection" target="_blank">Kaggle</a>.

YOLO is short for You Only Look Once. It is a family of single-stage deep learning based object detectors. They are capable of real-time object detection with state-of-the-art accuracy. Officially, as part of the Darknet framework, there are four versions of YOLO. Starting from YOLOv1 to YOLOv4. The Darknet framework is written in C and CUDA. YOLOv5 is the next version equivalent in the YOLO family. 

There are 5 YOLOv5 models. In this project, it is used YOLOv5m. This is the medium-sized model with 21.2 million parameters. It is perhaps the best suited model for a lot of datasets and training as it provides a good balance between speed and accuracy.

A dataset of fruits is used for training the custom YOLOv5 object detector. We can therefore detect 3 objects in images (+1 for the background class), including apples, bananas and oranges.

Data augmentation is implemented in the last experiments. Here, the dataset used for training is an aumented version of the fruits dataset: <a href="https://app.roboflow.com/ds/w115d8mw7V?key=H7V9pu9bcS" target="_blank">Augmented fruits</a>. Data Augmentation was generated in Roboflow with these specifications:
- Outputs per training example: 3
- Crop: 0% Minimum Zoom, 20% Maximum Zoom
- Rotation: Between -15° and +15°


## Instructions

Please, follow the instruction in the provided notebook.


## Outputs

Object detection videos are saved in:
```
 yolov5/runs/detect/
 ```
