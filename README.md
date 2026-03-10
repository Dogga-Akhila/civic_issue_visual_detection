# Civic Issue Visual Detection using YOLOv8

## Overview

Urban infrastructure problems such as garbage accumulation, road damage, pipeline leakage, and water stagnation significantly affect public health, transportation, and environmental quality. Manual monitoring of these issues is slow and inefficient.

This project develops an AI-based visual detection system that automatically identifies multiple civic infrastructure issues from images using the object detection model **YOLOv8** from **Ultralytics**.

The model is trained on a combination of publicly available datasets and detects several types of real-world civic problems from images captured in urban environments.

---

## Problem Statement

Government bodies and municipalities receive thousands of complaints related to infrastructure issues such as damaged roads, garbage dumping, pipeline leaks, and water logging. Manual inspection and categorization of these problems is time-consuming.

This project aims to build an automated computer vision system capable of detecting and classifying multiple civic issues from images in real time.

---

## Objectives

* Detect multiple civic issues from images using deep learning.
* Combine datasets from different sources into a unified training dataset.
* Train a robust object detection model for multi-class detection.
* Evaluate model performance using standard object detection metrics.

---

## Detected Classes

The trained model detects the following categories:

1. Garbage / Waste accumulation
2. Road Damage (potholes, cracks)
3. Pipeline Damage / Leakage
4. Water Stagnation / Water Logging

---

## Model Architecture

The project uses **YOLOv8 (You Only Look Once Version 8)**, a real-time object detection architecture developed by Ultralytics.

Key features:

* Anchor-free detection head
* Efficient backbone and neck architecture
* Real-time inference capability
* High accuracy for small and medium objects

---

## Dataset Sources

The training dataset was created by combining images from multiple sources, including:

* https://universe.roboflow.com/default-fx3sf/piles-of-litter/browse/fork?queryText=&pageSize=50&startingIndex=0&browseQuery=true --garbage

https://data.mendeley.com/datasets/c6f2b7mx9t/1 --road

https://universe.roboflow.com/nawaf-vh6hl/pipeline-defects_test-vpvly/browse?queryText=&pageSize=50&startingIndex=0&browseQuery=true --pipeline 

https://universe.roboflow.com/road-inspection/water-stagnation 


All annotations were converted into **YOLO format**.

---

## Project Structure

```
civic-issue-visual-detection/
│
├── notebooks
│   ├── kaggle_training.ipynb
│   └── local_experiments.ipynb
│
├── datasets 
│   ├── #all required datasets 
│
├── results
│   └── sample_predictions
│
├── requirements.txt
└── README.md
```

---

## Training Pipeline

### 1. Dataset Preparation

* Download datasets
* Convert annotations to YOLO format
* Merge datasets into a unified structure

### 2. Model Training

Training was performed using YOLOv8 with the following configuration:

* Image size: 640 × 640
* Batch size: 16
* Optimizer: SGD / Adam
* Epochs: configurable

Example training command:

```
yolo detect train model=yolov8n.pt data=data.yaml epochs=50 imgsz=640
```

---

## Evaluation Metrics

The model is evaluated using standard object detection metrics:

* **Precision**
* **Recall**
* **mAP@0.5**
* **mAP@0.5:0.95**

These metrics measure the detection accuracy and reliability of the model.

---

## Sample Results

Example predictions include:

* Garbage piles detected on roadsides
* Road potholes identified in street images
* Pipeline leak locations highlighted
* Water stagnation areas detected after rainfall

Bounding boxes are drawn around detected objects with confidence scores.

---

## Applications

Potential real-world applications include:

* Smart city monitoring systems
* Automated civic complaint verification
* Infrastructure maintenance planning
* Real-time surveillance of urban issues
* Integration with citizen complaint platforms

---

## Installation

Clone the repository:

```
git clone https://github.com/Dogga-Akhila/civic-issue-visual-detection.git
```

Install dependencies:

```
pip install -r requirements.txt
```

---

## Future Improvements

* Increase dataset diversity
* Improve detection for small objects
* Deploy the model as a web or mobile application
* Integrate with a civic complaint management system
* Real-time detection using live camera feeds

---

## Author

Akhila
BVRIT Narsapur
Department of Artificial Intelligence and Machine Learning

---

## License

This project is intended for educational and research purposes.
