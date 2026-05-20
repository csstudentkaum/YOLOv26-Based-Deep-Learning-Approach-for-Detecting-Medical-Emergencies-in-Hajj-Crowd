# CrowdShield 
### YOLOv26-Based Deep Learning Approach for Detecting Medical Emergencies in Hajj Crowd

---

## 📌 Overview

During Hajj, millions of pilgrims gather in a confined area, creating extreme crowd density. People can collapse from heat exhaustion or medical emergencies, yet security operators cannot monitor hundreds of camera feeds simultaneously — meaning collapsed individuals often go unnoticed until it is too late.

**CrowdShield** addresses this by fine-tuning a **YOLOv26** object detection model on annotated Hajj crowd images to **automatically detect collapsed persons in real time**. When a collapsed person is detected, an alert is triggered immediately, enabling rapid emergency response.

This project was developed as part of the **“Computer Vision for Developers”** program by SDAIA.


---

## 🎯 Classes

| Label | Description |
|---|---|
| `normal_person` | Standing or walking pilgrim |
| `Passed_out` | Collapsed person requiring assistance |

---

## 📂 Dataset

| Property | Details |
|---|---|
| **Source** | Roboflow — `hajj-data-tmiys` (v1) |
| **Images** | ~500+ annotated images |
| **Classes** | 2 (`normal_person`, `Passed_out`) |
| **Format** | YOLO annotations |
| **Image Size** | 640 × 640 |
| **Split** | Train / Validation / Test |
| **Scene Type** | Dense Hajj crowd scenes |

---

## 🗂️ Notebook Structure

| Section | Description |
|---|---|
| **1. Setup** | Install libraries (`ultralytics`, `roboflow`, `opencv-python`), verify GPU |
| **2. Dataset Loading** | Download dataset from Roboflow in YOLO format |
| **3. Dataset Exploration** | Sample images, class distribution, imbalance analysis |
| **4. Fine-Tuning** | Train two YOLOv26 model sizes, compare performance, select best |
| **5. Model Evaluation** | Metrics: mAP, Precision, Recall, F1 |
| **6. Visual Predictions** | Bounding-box overlays on sample images |
| **7. Speed Test** | Confirm inference speed is sufficient for live video |
| **8. Video Inference** | Run on a full video clip with an alert banner overlay |

---

## 🛠️ Tech Stack

- **Model:** YOLOv26 (via [Ultralytics](https://github.com/ultralytics/ultralytics))
- **Dataset Management:** [Roboflow](https://roboflow.com/)
- **Deep Learning Framework:** PyTorch
- **Environment:** Google Colab (Tesla T4 GPU)
- **Libraries:** `ultralytics`, `roboflow`, `opencv-python`, `numpy`, `matplotlib`, `PyYAML`

---

## 📊 Model Training

Two YOLOv26 model sizes are trained and compared to select the best trade-off between accuracy and inference speed. The chosen model is then evaluated on the held-out test set and applied to a real Hajj crowd video.

---

## 👥 Team

- **Manar Abdullah Alharbi**
- **Asma Sanad Almurashi**
