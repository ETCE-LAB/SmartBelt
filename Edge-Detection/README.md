# Material Edge Detection using YOLOv11 and Line Scan Camera

This repository provides a complete implementation of a YOLOv11-based material edge detection model, optimized for identifying **sharp vs. smooth edges** of metallic and plastic particles (1–4 mm) on a **moving conveyor belt** of an **Eddy Current Separator (BECS)** using a **monochrome line scan camera**, ELP camera and Raspberry Pi camera.

> This work is part of the "Twin-AI BECS" project for intelligent waste separation and fire risk mitigation in recycling systems.

---

##  Dataset

- **Source**: [Roboflow - LineScanEdgeDetection](https://universe.roboflow.com/ecs-hj1jt/linescanedgedetection)
- **Classes**: `sharp`, `smooth`
- **Image Type**: Monochrome line scan images + RGB image 
- **Format**: YOLO.v11 format
- **Data split**: 70% training / 20% validation / 10% test

---

##  Project Features

- Detection of **sharp** and **smooth** metallic materials
- Designed for **real-time** inference in industrial settings
- Based on **YOLOv11 architecture**
- Model exported and tested in`.pt` 

---

---

##  Requirements

Install the dependencies in a Python virtual environment:

```bash
pip install -r requirements.txt
```

##  Typical key packages:
- torchvision
- torch
- ultralytics
- opencv-python
- matplotlib
- numpy

##  How to Train
Clone the repository:
```
git clone https://github.com/ObscuraKrypta/Material-Edge-Detection.git
cd Material-Edge-Detection
```

## Train the model:
```
yolo task=detect mode=train model=yolov11.yaml data=data.yaml epochs=100 imgsz=640
```

# NOTE: 
You can adjust batch, imgsz, and epochs according to your system capacity.


## Inference / Testing:

To run inference on test images or live camera feed:

```
yolo task=detect mode=predict model=runs/train/exp/weights/best.pt source=test_images/
```

## Deployment Notes:
- For embedded deployment, convert the model to ONNX or TensorRT.
- The model is designed to process continuous line scan strips with minimal latency.


## Related Work:
# This model is part of a larger system including:

- Fire and smoke detection using thermal camera.
- AI-based optimization of drum and conveyor speeds.
- Auto belt misalignment correction.
- IoT-based remote control and alerting.


 ## Acknowledgments:

 Special thanks to Professor Daniel Goldmann and the IFAD Institute for their cooperation and support in providing access to the eddy current machine. We also sincerely appreciate the valuable assistance of technicians Jean-Marie Dornbusch and Olaf Tschenscher.


 ##  Contact:
 For questions, suggestions, or collaboration:
 
 Prof. Dr. Benjamin Leiding
 - Professor at DIGIT – Center for Digital Technologies -> benjamin.leiding@tu-clausthal.de
 
 Shohreh Kia
 - Researcher at DIGIT – Center for Digital Technologies -> shohreh.kia@tu-clausthal.de










