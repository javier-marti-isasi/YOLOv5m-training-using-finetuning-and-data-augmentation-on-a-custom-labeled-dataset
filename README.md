# YOLOv5m training using finetuning and data augmentation on a custom labeled dataset

Object detection YOLOv5m finetuning on custom dataset with PyTorch. The custom dataset was manually labeled in CVAT and preprocessed in Roboflow. Data augmentation is implemented in the last two experiments. Inference on images.

Original YOLOv5 repository <a href="https://github.com/ultralytics/yolov5" target="_blank">here</a>.

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

It is used a <a href="https://app.roboflow.com/ds/ReliRzR2PO?key=INYILG4hU7" target="_blank">Dataset of fruits</a> that was previouly labeled in CVAT and preprocessed in Roboflow. It consists of 300 images with apples, bananas and oranges labelled. This dataset will be used for training the custom YOLOv5 object detector. Original dataset is located in <a href="https://www.kaggle.com/datasets/mbkinaci/fruit-images-for-object-detection" target="_blank">Kaggle</a>.

Data preprocessing in Roboflow included the following specifications:
- Resize: Fit (black edges) in 416x416
- Auto-Orient: Applied

YOLO is short for You Only Look Once. It is a family of single-stage deep learning based object detectors. They are capable of real-time object detection with state-of-the-art accuracy. Officially, as part of the Darknet framework, there are four versions of YOLO. Starting from YOLOv1 to YOLOv4. The Darknet framework is written in C and CUDA. YOLOv5 is the next version equivalent in the YOLO family. 

There are 5 YOLOv5 models. In this project, it is used YOLOv5m. This is the medium-sized model with 21.2 million parameters. It is perhaps the best suited model for a lot of datasets and training as it provides a good balance between speed and accuracy.

A dataset of fruits is used for training the custom YOLOv5 object detector. We can therefore detect 3 objects in images (+1 for the background class), including apples, bananas and oranges.

Data augmentation is implemented in the last two experiments. Here, the dataset used for training is an aumented version of the fruits dataset: <a href="https://app.roboflow.com/ds/w115d8mw7V?key=H7V9pu9bcS" target="_blank">Augmented fruits</a>. Data Augmentation was generated in Roboflow with these specifications:
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
## Experiment results

Results of the 4 experiments in the best epoch:

<meta http-equiv="Content-Type" content="text/html; charset=utf-8"><link type="text/css" rel="stylesheet" href="resources/sheet.css" >
<div class="ritz grid-container" dir="ltr"><table class="waffle" cellspacing="0" cellpadding="0"><thead><tr><th class="row-header freezebar-vertical-handle"></th><th id="0C0" style="width:97px;" class="column-headers-background">A</th><th id="0C1" style="width:97px;" class="column-headers-background">B</th><th id="0C2" style="width:97px;" class="column-headers-background">C</th><th id="0C3" style="width:94px;" class="column-headers-background">D</th><th id="0C4" style="width:115px;" class="column-headers-background">E</th><th id="0C5" style="width:112px;" class="column-headers-background">F</th><th id="0C6" style="width:108px;" class="column-headers-background">G</th><th id="0C7" style="width:134px;" class="column-headers-background">H</th><th id="0C8" style="width:111px;" class="column-headers-background">I</th><th id="0C9" style="width:133px;" class="column-headers-background">J</th><th id="0C10" style="width:163px;" class="column-headers-background">K</th><th id="0C11" style="width:104px;" class="column-headers-background">L</th><th id="0C12" style="width:101px;" class="column-headers-background">M</th><th id="0C13" style="width:97px;" class="column-headers-background">N</th><th id="0C14" style="width:70px;" class="column-headers-background">O</th><th id="0C15" style="width:70px;" class="column-headers-background">P</th><th id="0C16" style="width:70px;" class="column-headers-background">Q</th></tr></thead><tbody><tr style="height: 20px"><th id="0R0" style="height: 20px;" class="row-headers-background"><div class="row-header-wrapper" style="line-height: 20px">1</div></th><td class="s0" dir="ltr">Experiment</td><td class="s0" dir="ltr">frozen layers</td><td class="s1" dir="ltr">Augment</td><td class="s0" dir="ltr">Best epoch</td><td class="s0" dir="ltr">train/box_loss</td><td class="s0" dir="ltr">train/obj_loss</td><td class="s0" dir="ltr">train/cls_loss</td><td class="s0" dir="ltr">metrics/precision</td><td class="s0" dir="ltr">metrics/recall</td><td class="s0" dir="ltr">metrics/mAP_0.5</td><td class="s0" dir="ltr">metrics/mAP_0.5:0.95</td><td class="s0" dir="ltr">val/box_loss</td><td class="s0" dir="ltr">val/obj_loss</td><td class="s0" dir="ltr">val/cls_loss</td><td class="s0" dir="ltr">x/lr0</td><td class="s0" dir="ltr">x/lr1</td><td class="s0" dir="ltr">x/lr2</td></tr><tr><th style="height:3px;" class="freezebar-cell freezebar-horizontal-handle"></th><td class="freezebar-cell"></td><td class="freezebar-cell"></td><td class="freezebar-cell"></td><td class="freezebar-cell"></td><td class="freezebar-cell"></td><td class="freezebar-cell"></td><td class="freezebar-cell"></td><td class="freezebar-cell"></td><td class="freezebar-cell"></td><td class="freezebar-cell"></td><td class="freezebar-cell"></td><td class="freezebar-cell"></td><td class="freezebar-cell"></td><td class="freezebar-cell"></td><td class="freezebar-cell"></td><td class="freezebar-cell"></td><td class="freezebar-cell"></td></tr><tr style="height: 20px"><th id="0R1" style="height: 20px;" class="row-headers-background"><div class="row-header-wrapper" style="line-height: 20px">2</div></th><td class="s2" dir="ltr">1</td><td class="s2" dir="ltr">18</td><td class="s3" dir="ltr">-</td><td class="s2" dir="ltr">314</td><td class="s2" dir="ltr">0.021722</td><td class="s2" dir="ltr">0.018552</td><td class="s2" dir="ltr">0.0033859</td><td class="s2" dir="ltr">0.89856</td><td class="s2" dir="ltr">0.91463</td><td class="s2" dir="ltr">0.92011</td><td class="s2" dir="ltr">0.77387</td><td class="s2" dir="ltr">0.018614</td><td class="s2" dir="ltr">0.0076953</td><td class="s2" dir="ltr">0.0025772</td><td class="s2" dir="ltr">0.0038026</td><td class="s2" dir="ltr">0.0038026</td><td class="s2" dir="ltr">0.0038026</td></tr><tr style="height: 20px"><th id="0R2" style="height: 20px;" class="row-headers-background"><div class="row-header-wrapper" style="line-height: 20px">3</div></th><td class="s2" dir="ltr">2</td><td class="s2" dir="ltr">15</td><td class="s3" dir="ltr">-</td><td class="s2" dir="ltr">279</td><td class="s2" dir="ltr">0.028924</td><td class="s2" dir="ltr">0.020846</td><td class="s2" dir="ltr">0.0081943</td><td class="s2" dir="ltr">0.86971</td><td class="s2" dir="ltr">0.84143</td><td class="s2" dir="ltr">0.89722</td><td class="s2" dir="ltr">0.72927</td><td class="s2" dir="ltr">0.022495</td><td class="s2" dir="ltr">0.0081846</td><td class="s2" dir="ltr">0.0079333</td><td class="s2" dir="ltr">0.0044956</td><td class="s2" dir="ltr">0.0044956</td><td class="s2" dir="ltr">0.0044956</td></tr><tr style="height: 20px"><th id="0R3" style="height: 20px;" class="row-headers-background"><div class="row-header-wrapper" style="line-height: 20px">4</div></th><td class="s2" dir="ltr">3</td><td class="s2" dir="ltr">15</td><td class="s3" dir="ltr">x3</td><td class="s2" dir="ltr">296</td><td class="s2" dir="ltr">0.021811</td><td class="s2" dir="ltr">0.020827</td><td class="s2" dir="ltr">0.002023</td><td class="s2" dir="ltr">0.96746</td><td class="s2" dir="ltr">0.91351</td><td class="s2" dir="ltr">0.96465</td><td class="s2" dir="ltr">0.692</td><td class="s2" dir="ltr">0.021847</td><td class="s2" dir="ltr">0.0079197</td><td class="s2" dir="ltr">0.0014771</td><td class="s2" dir="ltr">0.004159</td><td class="s2" dir="ltr">0.004159</td><td class="s2" dir="ltr">0.004159</td></tr><tr style="height: 20px"><th id="0R4" style="height: 20px;" class="row-headers-background"><div class="row-header-wrapper" style="line-height: 20px">5</div></th><td class="s2" dir="ltr">4</td><td class="s2" dir="ltr">18</td><td class="s3" dir="ltr">x3</td><td class="s2" dir="ltr">191</td><td class="s2" dir="ltr">0.032958</td><td class="s2" dir="ltr">0.024293</td><td class="s2" dir="ltr">0.0092162</td><td class="s2" dir="ltr">0.96116</td><td class="s2" dir="ltr">0.8889</td><td class="s2" dir="ltr">0.94326</td><td class="s2" dir="ltr">0.68581</td><td class="s2" dir="ltr">0.023283</td><td class="s2" dir="ltr">0.0079349</td><td class="s2" dir="ltr">0.0029014</td><td class="s2" dir="ltr">0.006238</td><td class="s2" dir="ltr">0.006238</td><td class="s2" dir="ltr">0.006238</td></tr></tbody></table></div>

## Inference of Experiment 3

![all](https://user-images.githubusercontent.com/73080100/182854011-5081b21c-1f8b-47a3-b834-708ac9dc9f69.jpg)
