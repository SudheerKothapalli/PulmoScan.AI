# 🫁 PulmoScan AI

![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-2.0+-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-3.0+-000000?style=for-the-badge&logo=flask&logoColor=white)
![Status](https://img.shields.io/badge/Status-Live-00d4aa?style=for-the-badge)

### AI-Powered Lung CT Scan Analysis
**Segmentation · Classification · GradCAM · Doctor's Report**

🔗 **Live Demo → [sudheerkothapalli.github.io/PulmoScan.AI](https://sudheerkothapalli.github.io/PulmoScan.AI)**

---

## 🧠 What is PulmoScan AI?

PulmoScan AI is a deep learning web application that analyzes chest CT scan images to detect and classify lung cancer. Upload any CT scan image and the system automatically runs segmentation, classification across 4 models, GradCAM visualization, and generates a complete clinical report — all in one click.

---

## ⚡ Live Demo

**[https://sudheerkothapalli.github.io/PulmoScan.AI](https://sudheerkothapalli.github.io/PulmoScan.AI)**

> Upload a CT scan → Click Run Full Analysis → Get real AI results instantly

---

## 🔬 How It Works
```
CT Scan Image
      │
      ▼
U-Net Segmentation  ←  Isolates lung region (ResNet34 encoder)
      │
      ▼
4 Classification Models
  ├── ResNet-50       →  87.4%
  ├── ResNet-101      →  89.2%
  ├── GoogLeNet       →  84.6%
  └── EfficientNet-B0 →  92.7% 👑 BEST
      │
      ▼
GradCAM Heatmap  ←  Shows where AI looked (per model)
      │
      ▼
Diagnostic Report
  ├── Cancer Type + Confidence %
  ├── Probability bars (all 4 classes)
  ├── Clinical Recommendations
  ├── Confusion Matrix
  ├── ROC Curves + AUC scores
  └── Precision · Recall · F1 per class
```

---

## 🎯 Cancer Types Detected

| Type | Origin | Urgency | 5-Year Survival |
|------|---------|---------|-----------------|
| 🟢 **Normal** | No malignancy found | LOW | N/A |
| 🔴 **Adenocarcinoma** | Peripheral alveoli | HIGH | Stage I: 70–80% |
| 🔴 **Large Cell Carcinoma** | Undifferentiated cells | HIGH | Stage I: ~55% |
| 🟠 **Squamous Cell Carcinoma** | Central bronchial epithelium | HIGH | Stage I: 60–70% |

---

## 📊 Model Performance

| Model | Accuracy | Precision | Recall | F1 Score |
|-------|----------|-----------|--------|----------|
| ResNet-50 | 87.4% | 86.1% | 87.0% | 86.5% |
| ResNet-101 | 89.2% | 88.4% | 89.0% | 88.7% |
| GoogLeNet | 84.6% | 83.5% | 84.1% | 83.8% |
| **EfficientNet-B0** 👑 | **92.7%** | **92.0%** | **92.5%** | **92.2%** |

---

## ✨ Features

| Feature | Description |
|---------|-------------|
| 🫁 CT Upload | Drag and drop PNG, JPG, DICOM images |
| 🔍 U-Net Segmentation | Automatically isolates lung from CT scan |
| 📦 ROI Localisation | Bounding box around detected lung region |
| 🤖 4 AI Models | ResNet50, ResNet101, GoogLeNet, EfficientNet-B0 |
| 🔥 GradCAM | Visual heatmap showing AI attention per model |
| 📊 Confusion Matrix | Per model per class performance grid |
| 📈 ROC Curves | AUC scores for all 4 cancer classes |
| 🎯 Precision Recall F1 | Detailed metrics per class per model |
| 🩺 Doctor Report | Clinical advice and treatment options |
| 💊 Cancer Details | Definition, stages, causes, survival stats |

---

## 🗂️ Datasets

| Dataset | Source | Used For |
|---------|--------|----------|
| Finding Lungs in CT Data | [Kaggle kmader](https://www.kaggle.com/datasets/kmader/finding-lungs-in-ct-data) | U-Net segmentation training |
| Chest CT-Scan Images | [Kaggle mohamedhanyyy](https://www.kaggle.com/datasets/mohamedhanyyy/chest-ctscan-images) | Cancer classification training |

---

## 🛠️ Tech Stack

**Frontend**
- HTML5, CSS3, Vanilla JavaScript
- Canvas API for image rendering
- GradCAM overlay visualization
- Dark clinical UI theme

**Backend**
- PyTorch 2.0+
- segmentation-models-pytorch (U-Net)
- EfficientNet-PyTorch
- pytorch-grad-cam
- Flask REST API
- OpenCV, NumPy, Pillow
- scikit-learn for metrics

---

## 🚀 Run Locally

**1. Clone Repository**
```bash
git clone https://github.com/SudheerKothapalli/PulmoScan.AI.git
cd PulmoScan.AI
```

**2. Install Dependencies**
```bash
pip install torch torchvision segmentation-models-pytorch efficientnet_pytorch grad-cam flask flask-cors opencv-python numpy pillow kagglehub scikit-learn
```

**3. Train Models**
```bash
# Run all 16 cells in Google Colab
# Requires Kaggle API key and T4 GPU
# Training time approximately 90 minutes
```

**4. Start Backend**
```bash
python app.py
```

**5. Open Web App**
```
Open index.html in browser
```

---

## 📁 Project Structure
```
PulmoScan.AI/
├── index.html              ← Full frontend web app
├── app.py                  ← Flask backend API
├── README.md               ← This file
├── unet_lung.pth           ← U-Net weights
├── resnet50_clf.pth        ← ResNet-50 weights
├── resnet101_clf.pth       ← ResNet-101 weights
├── googlenet_clf.pth       ← GoogLeNet weights
└── efficientnet_clf.pth    ← EfficientNet-B0 weights 👑
```

---

## ⚠️ Medical Disclaimer

This tool is for **research and educational purposes only.**
Results are **NOT a substitute** for professional medical diagnosis.
Always consult a qualified **radiologist or oncologist.**
Model outputs may contain errors.

---

## 👨‍💻 Author

**Sudheer Kothapalli**

- GitHub : [SudheerKothapalli](https://github.com/SudheerKothapalli)
- Project : [PulmoScan.AI](https://sudheerkothapalli.github.io/PulmoScan.AI)

---

## 📄 License

MIT License — Free to use for research and educational purposes.

---

Built with ❤️ for medical AI research

⭐ Star this repo if you found it helpful!

`PyTorch` · `U-Net` · `EfficientNet` · `GradCAM` · `Flask`
