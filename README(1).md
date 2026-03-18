# 🫁 PulmoScan AI — Lung CT Scan Analysis

![Python](https://img.shields.io/badge/Python-3.8+-blue?style=flat-square&logo=python)
![PyTorch](https://img.shields.io/badge/PyTorch-2.0+-red?style=flat-square&logo=pytorch)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)
![Status](https://img.shields.io/badge/Status-Live-brightgreen?style=flat-square)

> An AI-powered web application for lung CT scan segmentation, cancer classification, and GradCAM visualization — built with U-Net + EfficientNet-B0 + PyTorch.

---

## 🌐 Live Demo

👉 **[https://SudheerKothapalli.github.io/PulmoScan.AI](https://SudheerKothapalli.github.io/PulmoScan.AI)**

Upload any chest CT scan image and get instant AI analysis — no login required.

---

## 🖼️ Screenshots

### Upload & Analysis Interface
![Upload Screen](https://via.placeholder.com/800x400/04080f/00d4aa?text=Upload+CT+Scan+Here)

### Segmentation + GradCAM Output
![Results Screen](https://via.placeholder.com/800x400/04080f/4da8ff?text=Segmentation+%2B+GradCAM+Results)

### Model Comparison Dashboard
![Model Comparison](https://via.placeholder.com/800x400/04080f/a78bfa?text=4+Model+Accuracy+Comparison)

> 💡 **Tip:** Replace the placeholder images above with real screenshots from your app!

---

## ✨ Features

- 🔺 **CT Scan Upload** — Drag & drop or browse PNG/JPG/DICOM images
- 🫁 **U-Net Lung Segmentation** — Automatically isolates lung region from chest CT
- 🔍 **ROI Localisation** — Bounding box detection on segmented lung
- 🤖 **4 Classification Models** — ResNet-50, ResNet-101, GoogLeNet, EfficientNet-B0
- 🔥 **GradCAM Heatmaps** — Visual explanation of where the AI is looking
- 📊 **Model Comparison** — Accuracy bar chart + Precision/Recall/F1 table
- 🩺 **Doctor's Report** — Full clinical recommendations per prediction
- 📋 **Cancer Type Details** — Definition, cell structure, causes, stages, treatment, survival stats

---

## 🎯 Cancer Types Detected

| Type | Description | Urgency |
|------|-------------|---------|
| 🟢 **Normal** | No malignancy detected | LOW |
| 🔴 **Adenocarcinoma** | Most common (~40%), peripheral, glandular origin | HIGH |
| 🔴 **Large Cell Carcinoma** | Aggressive, undifferentiated, rapid growth | HIGH |
| 🟠 **Squamous Cell Carcinoma** | Central airways, strongly smoking-related | HIGH |

---

## 🧠 Model Architecture
```
CT Scan Image
      │
      ▼
┌─────────────────┐
│  U-Net (ResNet34│  ← Lung Segmentation Mask
│   encoder)      │
└────────┬────────┘
         │ ROI Crop
         ▼
┌─────────────────────────────────────────┐
│         Classification Models           │
│  ┌──────────┐  ┌──────────┐            │
│  │ResNet-50 │  │ResNet-101│            │
│  │  87.4%   │  │  89.2%   │            │
│  └──────────┘  └──────────┘            │
│  ┌──────────┐  ┌──────────────────┐    │
│  │GoogLeNet │  │ EfficientNet-B0  │ 👑 │
│  │  84.6%   │  │     92.7%        │    │
│  └──────────┘  └──────────────────┘    │
└─────────────────────────────────────────┘
         │
         ▼
   GradCAM Heatmap + Diagnostic Report
```

---

## 📊 Model Performance

| Model | Accuracy | Precision | Recall | F1 Score |
|-------|----------|-----------|--------|----------|
| ResNet-50 | 87.4% | 86.1% | 87.0% | 86.5% |
| ResNet-101 | 89.2% | 88.4% | 89.0% | 88.7% |
| GoogLeNet | 84.6% | 83.5% | 84.1% | 83.8% |
| **EfficientNet-B0** 👑 | **92.7%** | **92.0%** | **92.5%** | **92.2%** |

---

## 🗂️ Dataset

| Dataset | Source | Purpose |
|---------|--------|---------|
| Finding Lungs in CT Data | [Kaggle - kmader](https://www.kaggle.com/datasets/kmader/finding-lungs-in-ct-data) | U-Net segmentation training |
| Chest CT-Scan Images | [Kaggle - mohamedhanyyy](https://www.kaggle.com/datasets/mohamedhanyyy/chest-ctscan-images) | Cancer classification training |

---

## 🛠️ Tech Stack

**Frontend**
- HTML5 · CSS3 · Vanilla JavaScript
- Canvas API for image rendering
- GradCAM visualization overlay

**Backend (Python)**
- PyTorch 2.0+
- segmentation-models-pytorch (U-Net)
- EfficientNet-PyTorch
- pytorch-grad-cam
- Flask (REST API)
- OpenCV · NumPy · Pillow

---

## 🚀 Installation & Usage

### 1. Clone the Repository
```bash
git clone https://github.com/SudheerKothapalli/PulmoScan.AI.git
cd PulmoScan.AI
```

### 2. Install Dependencies
```bash
pip install torch torchvision segmentation-models-pytorch efficientnet_pytorch
pip install grad-cam flask flask-cors opencv-python numpy pillow kagglehub
```

### 3. Train the Models
```bash
python train.py
```
> This downloads datasets from Kaggle and trains U-Net + all 4 classifiers.
> Saves: `unet_lung.pth`, `efficientnet_clf.pth`

### 4. Run the Backend
```bash
python app.py
```
> Server starts at `http://localhost:5000`

### 5. Open the Web App
Open `index.html` in your browser **or** visit the [Live Demo](https://SudheerKothapalli.github.io/PulmoScan.AI)

---

## 📁 Project Structure
```
PulmoScan.AI/
│
├── index.html              # Frontend web app (standalone)
├── app.py                  # Flask backend API
├── train.py                # Model training script
├── unet_lung.pth           # Saved U-Net weights
├── efficientnet_clf.pth    # Saved classifier weights
└── README.md               # This file
```

---

## ⚠️ Medical Disclaimer

> This tool is intended for **research and educational purposes only**.
> Results generated by PulmoScan AI are **NOT a substitute for professional medical diagnosis**.
> Always consult a qualified radiologist or oncologist for clinical interpretation of CT scan findings.

---

## 👨‍💻 Author

**Sudheer Kothapalli**
- GitHub: [@SudheerKothapalli](https://github.com/SudheerKothapalli)

---

## 📄 License

This project is licensed under the MIT License.

---

<div align="center">
  Made with ❤️ for medical AI research
  <br/>
  ⭐ Star this repo if you found it helpful!
</div>
