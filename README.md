# YOLOv8 Grocery Product Detection

This project uses **YOLOv8** to detect grocery items in real-time images, intended as a component of a **barcode-free smart checkout system**. It can also be extended to support **OCR** and **EfficientNet**-based classification downstream.

---

## 📦 Project Overview

- **Object Detection**: Trained using Ultralytics YOLOv8 on a custom dataset of grocery items.
- **Goal**: Identify multiple grocery products per frame for real-time checkout or inventory applications.
- **Input Format**: Images of grocery products (single or multiple items).
- **Output Format**: Detected objects with bounding boxes and class names.

---

## 📁 Repository Structure
```bash
yolov8-grocery-model/
│
├── yolov8_outputs/ # Exported results from runs/detect/
│ ├── train/ # YOLOv8 training results
│ │ ├──  weights/
│ │ │ ├── best.pt # Best model weights (to reuse)
│ │ │ └── last.pt # Last epoch weights
│ │ ├──  results.csv
│ │ ├──  labels.jpg # Label distribution
│ │ └──  args.yaml / opt.yaml # Training configuration
│ └── predict/ # Sample inference results
│ └── data.yaml # Class names and dataset structure
│
├── README.md # You’re here!
```

---

## 🧠 Model Details

- **Model**: `YOLOv8n` (Nano) for faster training and inference
- **Dataset**: Custom grocery image set with bounding box annotations
- **Classes**: Detected using custom `data.yaml` config

---

## 🚀 How to Use

### 1. Clone this repository

```bash
git clone https://github.com/ChristinaTUNA/yolov8-grocery-model.git
cd yolov8-grocery-model
```

### 2. Load the trained model
You can load the model using Ultralytics CLI or Python API:

```bash
from ultralytics import YOLO
model = YOLO("yolov8_outputs/train/weights/best.pt")
results = model.predict("your_image.jpg", conf=0.5)
```

### 3. Modify / extend
-Replace test images

-Improve with OCR (for text on packaging)

-Integrate EfficientNet for finer classification

-Hook into a mobile app, API, or checkout interface

---

🧩 Future Integration
Component	Description
🔠 OCR	Read product labels, expiry dates
🧠 EfficientNet	Classify similar-looking items more precisely
📱 Mobile App	Grocery assistant or self-checkout UI
☁️ Cloud API	For large-scale inference

---

📝 License
This project is open-source and may be adapted for educational and research purposes. Contact for commercial use.


---

Let me know if you'd like to include:

- A sample image (you can upload one and link it)
- A short video of model inference
- A separate section for EfficientNet/OCR roles

Or I can generate a second version tailored for project presentation slides.
