# 🦺 AI-Based Worker Safety Monitoring Using YOLO11

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)
![YOLO11](https://img.shields.io/badge/YOLO-v11-green)
![OpenCV](https://img.shields.io/badge/OpenCV-Computer%20Vision-red?logo=opencv)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)
![License](https://img.shields.io/badge/License-MIT-yellow)

## Overview

An AI-based worker-safety monitoring project using **YOLO11** for safety-helmet detection in images and video. The project demonstrates dataset preparation, object-detection training, evaluation, and inference with Python, Ultralytics, OpenCV, and Jupyter.

## Features

- Helmet detection on images and video sources
- YOLO11-based object detection
- Training and evaluation workflow
- Saved model weights for inference
- Jupyter-based experimentation

## Tech stack

| Technology | Purpose |
|---|---|
| Python | Development |
| YOLO11 / Ultralytics | Object detection |
| OpenCV | Image/video processing |
| PyTorch | Model runtime |
| Jupyter | Experimentation |
| NumPy / Matplotlib | Data and visualization |

## Project structure

```text
AI-Based-Worker-Safety-Monitoring-Using-YOLO11/
├── Ai_based_safety_monitoring.ipynb
├── best.pt
├── yolov11_config.yaml
├── test-imgs/
├── train-18/
├── requirements.txt
└── README.md
```

## Reproducible setup

Use Python 3.10 for the environment used during development.

```bash
git clone https://github.com/rudra5090/AI-Based-Worker-Safety-Monitoring-Using-YOLO11.git
cd AI-Based-Worker-Safety-Monitoring-Using-YOLO11
python -m pip install -r requirements.txt
```

If you use Jupyter, register the environment as a kernel before opening the notebook.

## Run inference

```python
from ultralytics import YOLO

model = YOLO("best.pt")
results = model.predict(source="test-imgs", conf=0.25, save=True)
```

## Training

The training configuration is stored in `yolov11_config.yaml`. A representative Ultralytics training call is:

```python
from ultralytics import YOLO

model = YOLO("yolo11n.pt")
model.train(data="yolov11_config.yaml", epochs=50, imgsz=640)
```

## Evaluation

The repository includes training artifacts under `train-18/`. When reporting model performance, use the metrics from the final training run and record the dataset split, image size, epoch count, and model checkpoint so results remain reproducible.

## Troubleshooting

- If `cv2.imshow()` is unavailable in Jupyter, display saved inference output instead.
- If the notebook uses a different Python interpreter, select the environment containing Ultralytics and OpenCV.
- Keep large model artifacts and datasets documented clearly so another developer knows which files are required.

## Applications

- Construction-site PPE monitoring
- Manufacturing safety checks
- Warehouse safety monitoring
- Industrial computer-vision experiments

## Future improvements

- Detect additional PPE such as safety vests
- Add person tracking
- Add live CCTV monitoring
- Add alert notifications
- Explore cloud deployment

## Author

**Rudranarayan Debata** — [GitHub](https://github.com/rudra5090)

## License

This project is licensed under the MIT License.
