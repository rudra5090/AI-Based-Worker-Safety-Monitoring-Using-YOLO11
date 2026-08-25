# 🦺 AI-Based Worker Safety Monitoring Using YOLO11

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)
![YOLO11](https://img.shields.io/badge/YOLO-v11-green)
![OpenCV](https://img.shields.io/badge/OpenCV-Computer%20Vision-red?logo=opencv)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)
![License](https://img.shields.io/badge/License-MIT-yellow)

> **Real-time AI-based PPE safety monitoring using YOLO11 and OpenCV.**

## 📌 Project Overview

This project presents an **AI-Based Worker Safety Monitoring System** using the **YOLO11 object detection model** to detect safety-helmet compliance from images and video streams.

The system is designed as a practical computer-vision prototype for industrial environments such as construction sites, factories, warehouses, and manufacturing facilities.

## 🎥 Live Demo

The screenshots below show the model running locally through a Jupyter/OpenCV workflow and producing an **UNSAFE** safety-status result when a helmet is not detected.

> **Repository note:** place the two supplied screenshots in `docs/images/` using the filenames shown below. The README is already prepared to display them.

### Detection Demo — Unsafe Condition

<img src="docs/images/helmet-detection-demo-1.jpg" alt="YOLO11 worker safety helmet detection demo showing unsafe condition" width="800">

### Detection Demo — Local Jupyter/OpenCV Run

<img src="docs/images/helmet-detection-demo-2.jpg" alt="YOLO11 worker safety monitoring running locally" width="700">

## 🧠 How It Works

```text
                 ┌─────────────────────┐
                 │ Camera / Image /    │
                 │ Video Input         │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │ OpenCV              │
                 │ Frame Processing    │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │ YOLO11              │
                 │ Object Detection    │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │ Helmet Detection    │
                 │ + Confidence Score  │
                 └──────────┬──────────┘
                            │
                  ┌─────────┴─────────┐
                  ▼                   ▼
             ┌──────────┐       ┌──────────┐
             │  SAFE    │       │  UNSAFE  │
             │ Helmet   │       │ No helmet│
             │ detected │       │ detected │
             └──────────┘       └──────────┘
```

## 🎯 Objectives

- Detect workers wearing safety helmets.
- Identify unsafe/no-helmet conditions.
- Provide near-real-time visual safety feedback.
- Reduce reliance on manual PPE inspection.
- Demonstrate practical deployment of YOLO11 for workplace safety.

## 🚀 Features

- ✅ YOLO11-based object detection
- ✅ Image and video inference
- ✅ OpenCV integration
- ✅ Helmet-safety status output
- ✅ Confidence-based detection
- ✅ Jupyter Notebook workflow
- ✅ Training and evaluation artifacts
- 🔄 Future-ready for CCTV and alert integration

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Python | Core programming |
| YOLO11 | Object detection |
| Ultralytics | YOLO training/inference framework |
| OpenCV | Image/video processing |
| NumPy | Numerical operations |
| Matplotlib | Training/evaluation visualization |
| Jupyter | Experimentation and demonstration |

## 📂 Project Structure

```text
AI-Based-Worker-Safety-Monitoring-Using-YOLO11/
│
├── Ai_based_safety_monitoring.ipynb
├── best.pt
├── yolov11_config.yaml
├── requirements.txt
├── test-imgs/
├── train-18/
│   ├── results.png
│   └── confusion_matrix.png
├── docs/
│   └── images/
│       ├── helmet-detection-demo-1.jpg
│       └── helmet-detection-demo-2.jpg
└── README.md
```

## 📊 Model Performance

The repository's current documented evaluation results are:

| Metric | Value |
|---|---:|
| Precision | **96.13%** |
| Recall | **95%** |
| mAP@50 | **96%** |
| Framework | **YOLO11** |

> Results can vary with dataset composition, confidence threshold, camera angle, lighting, and hardware.

## 📷 Training Results

### Training Curves

<img src="train-18/results.png" alt="YOLO11 training results" width="800">

### Confusion Matrix

<img src="train-18/confusion_matrix.png" alt="YOLO11 confusion matrix" width="700">

## 💻 Installation

### 1. Clone the repository

```bash
git clone https://github.com/rudra5090/AI-Based-Worker-Safety-Monitoring-Using-YOLO11.git
cd AI-Based-Worker-Safety-Monitoring-Using-YOLO11
```

### 2. Create an environment

Python **3.10** is recommended for the documented setup.

```bash
python -m venv .venv
```

Windows:

```bash
.venv\Scripts\activate
```

Linux/macOS:

```bash
source .venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

## ▶️ Run the Project

Open the notebook:

```bash
jupyter notebook
```

Then open:

```text
Ai_based_safety_monitoring.ipynb
```

Run the cells for model loading, inference, and evaluation.

## 🏋️ Training

Example Ultralytics training workflow:

```python
from ultralytics import YOLO

model = YOLO("yolo11n.pt")

model.train(
    data="yolov11_config.yaml",
    epochs=50,
    imgsz=640
)
```

## 🔍 Prediction

```python
from ultralytics import YOLO

model = YOLO("best.pt")

results = model.predict(
    source="test-imgs",
    conf=0.25,
    save=True
)
```

## ⚠️ Limitations

- Detection quality depends on lighting, camera angle, distance, and image quality.
- A single-class helmet detector does not provide complete PPE compliance monitoring.
- Real-world deployment should be validated on representative workplace footage before operational use.
- The current project is a research/portfolio prototype rather than a certified workplace-safety system.

## 🔮 Roadmap

- [ ] Live CCTV stream support
- [ ] Person tracking
- [ ] Helmet + safety-vest detection
- [ ] Violation screenshots and timestamps
- [ ] Real-time dashboard
- [ ] Email/notification alerts
- [ ] Prediction history database
- [ ] Docker deployment
- [ ] Cloud deployment

## 🌟 Applications

- Construction sites
- Manufacturing facilities
- Smart factories
- Mining environments
- Warehouses
- Industrial PPE monitoring

## 👨‍💻 Author

**Rudranarayan Debata**  
Computer Science Engineering Student

GitHub: https://github.com/rudra5090

## 📜 License

This project is licensed under the MIT License.
