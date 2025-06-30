# Intelligent Monitoring of BECS Conveyors via Vision and the IoT for Safety and Separation Efficiency


## Overview

This repository accompanies the research paper:

This research proposes an intelligent, real-time monitoring system for **Barrier Eddy Current Separator (BECS)** conveyor belts, aiming to enhance **worker safety**, **equipment longevity**, and **material separation efficiency** through the integration of:

- **Thermal imaging** for early fire hazard detection
- **Machine vision** for conveyor belt misalignment correction
- **Deep learning models (YOLOv11n-seg)** for material shape analysis
- **IoT-based alerting** for immediate risk communication

---

## Project Components

### Thermal Hazard Detection
- Uses the **MLX90640 thermal camera** to monitor surface temperature of the conveyor, especially above the magnetic drum.
- Automatically triggers alerts when a temperature exceeds a safety threshold (e.g., >40°C).
- Sends real-time warning messages via **Telegram bot** and activates a **buzzer** for on-site alerts.

### Conveyor Belt Misalignment Detection & Correction
- Captures conveyor edges with a **Raspberry Pi camera**.
- Detects white alignment lines using **OpenCV** (Canny + Hough transform).
- Corrects misalignment using **stepper motors** without interrupting the system.
- Optimizations include **Gaussian Blur** and **Region of Interest (ROI)** for performance.

### Shape Detection via YOLOv11n-seg
- Distinguishes **sharp** vs. **smooth** materials (1–4 mm) on the conveyor belt using **YOLOv11n-seg**.
- Trained on over **2500 annotated images** using Roboflow.
- Integrates a geometric post-processing layer for edge sharpness analysis using `approxPolyDP`.

### IoT-Based Alert System
- Combines sensor outputs to create a multi-tiered alerting system (local buzzer + Telegram API).
- Supports **predictive maintenance** by learning from temperature trends and shape patterns.

---

## Technical Stack

| Component                | Technology Used             |
|-------------------------|-----------------------------|
| Programming Language    | Python 3.11.7               |
| ML/AI Framework         | YOLOv11n-seg (Ultralytics 8.3.53) |
| Hardware                | Raspberry Pi, MLX90640, Stepper Motors |
| Libraries               | OpenCV, PyTorch, Roboflow, Telegram API |
| Dataset Tool            | Roboflow for labeling and segmentation |
| Model Output            | Shape classification (sharp vs. smooth), segmentation masks |

---

## Dataset

- Custom-built dataset of 519 images with 1105 instances.
- Classes: `sharp`, `smooth`
- Annotations: Polygon masks (via Roboflow)
- **YOLOv11n-seg Model Accuracy**:
  - **mAP@0.5**: 91.4%
  - **Mask Precision**: 87.8%
  - **Average Inference Time**: ~6.7 ms/image

---

## Results Summary

### Misalignment Correction
- Detection accuracy: >90% across various lighting/vibration conditions
- Average detection time: ~0.028s
- Motor correction latency: ~0.03–0.05s

### Fire Detection
- Alert accuracy: 97%
- Response time: 1.7–2.5 seconds
- Maximum recorded temperature: 45.3°C (iron contamination)

### Shape Detection
- Classification precision: 
  - Sharp: 86.4%
  - Smooth: 87.3%
- Inference speed: ~4.9 ms per image

---

## Visual Examples

![YOLOv11n-seg Detection](./assets/yolov11-seg-example.png)  
*Accurate classification of sharp vs. smooth objects on a conveyor belt.*


