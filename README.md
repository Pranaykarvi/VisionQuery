# 🎯 Intelligent Video Search with Object Detection & Natural Language Queries

A full pipeline to upload or stream videos, write natural language queries, and automatically detect relevant frames or moments using YOLOv8 and NLP.

> ✨ Example Query: _"Find people near red cars"_  
> 📦 Powered by: YOLOv8 + OpenCV + Ultralytics + spaCy

---

## 🚀 Features

- Upload video footage or use a live webcam stream
- Type natural language queries to search objects/scenes
- Uses YOLOv8 for real-time or batch object detection
- Maps queries to object labels using NLP (spaCy)
- Returns matched frames with timestamps or short clips

---

## 🧠 Tech Stack

### 🔍 Model & Detection
- [YOLOv8 (Ultralytics)](https://docs.ultralytics.com)
- [OpenCV](https://opencv.org/) – Live feed & frame parsing
- [Albumentations](https://albumentations.ai/) – Data augmentation
- [spaCy](https://spacy.io/) – Query parsing and label mapping

### 🌐 Backend & Deployment
- Python (FastAPI / Flask)
- Torch + CUDA (for GPU training/inference)
- Google Colab / AWS EC2 for training
- PostgreSQL / Redis (Optional: for search history / caching)

---

## 📂 Directory Structure

```
project-root/
├── datasets/
│ └── custom_dataset/
├── models/
│ └── yolov8n.pt
├── app/
│ ├── main.py
│ ├── query_parser.py
│ └── detect.py
├── notebooks/
│ └── yolo_training.ipynb
├── static/
│ └── outputs/
├── README.md
└── requirements.txt
```

---

## 📦 Datasets

### Recommended:

- **COCO**: 80 base classes for general objects.
- **Open Images V7**: Larger, more specific label set.
- **Custom**: Use `LabelImg` or [Roboflow](https://roboflow.com) for labeling.

Prepare dataset in YOLO format:

```bash
datasets/
└── custom_dataset/
    ├── images/
    │   ├── train/
    │   └── val/
    └── labels/
        ├── train/
        └── val/
```
## 🏋️ Model Training
Using Ultralytics YOLOv8:
```
# Install ultralytics
pip install ultralytics

# Train the model
yolo detect train data=data.yaml model=yolov8n.pt epochs=50 imgsz=640 batch=16
```

## 🧾 Requirements
```
ultralytics
opencv-python
torch
numpy
matplotlib
spacy
albumentations
```
## 📜 License
This project is licensed under the MIT License.
