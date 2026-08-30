# 🫁 PulmoScan.AI
### Lung Cancer Detection Using Deep Learning and Explainable AI

PulmoScan.AI is a deep learning-based medical image analysis application developed to detect and classify lung cancer from **CT scan images**.

The system combines **CT image preprocessing, U-Net based lung segmentation, transfer-learning-based CNN classification, and Grad-CAM explainability** to provide an interpretable prediction pipeline.

> **Domain:** Deep Learning | Computer Vision | Medical Image Processing | Explainable AI

---

## 📌 Project Overview

Lung cancer detection from medical images is a challenging computer vision problem because abnormalities can vary significantly in size, shape, texture, and location.

PulmoScan.AI addresses this problem through a multi-stage deep learning pipeline:

**CT Scan → Preprocessing → Lung Segmentation → CNN Classification → Grad-CAM → Prediction**

The system is designed as an educational and research-oriented prototype for automated lung cancer image analysis.

---

## 🎯 Objectives

- Develop an automated lung cancer classification system using CT scan images.
- Segment the lung region before classification.
- Apply transfer learning using multiple CNN architectures.
- Compare the performance of different deep learning models.
- Provide visual explanations using Grad-CAM.
- Integrate the trained pipeline into a web-based application.

---

## 🏗️ System Architecture

The proposed system consists of four major stages:

### 1. CT Image Preprocessing

Input CT images undergo preprocessing techniques such as:

- Noise reduction
- CLAHE-based contrast enhancement
- Pixel normalization
- Image resizing
- Data augmentation

These steps improve image quality and provide standardized inputs for the deep learning models.

### 2. Lung Segmentation

A **U-Net architecture with a ResNet-34 backbone** is used for semantic segmentation of the lung region.

The segmentation stage helps the classification models focus on the relevant anatomical region.

### 3. Multi-Model CNN Classification

Transfer learning is applied using multiple convolutional neural network architectures:

- ResNet-50
- ResNet-101
- GoogLeNet
- EfficientNet-B0

The models are trained and evaluated for multi-class lung cancer classification.

### 4. Explainable AI with Grad-CAM

**Grad-CAM (Gradient-weighted Class Activation Mapping)** is used to visualize the regions of the CT image that contribute most strongly to the model's prediction.

This provides a visual explanation of the classification result instead of presenting only a predicted class.

---

## 🧠 Deep Learning Models

| Model | Purpose |
|---|---|
| U-Net + ResNet-34 | Lung segmentation |
| ResNet-50 | Cancer classification |
| ResNet-101 | Cancer classification |
| GoogLeNet | Cancer classification |
| EfficientNet-B0 | Cancer classification |
| Grad-CAM | Model explainability |

---

## 🧬 Classification Categories

The classification pipeline is designed for the following categories:

- Adenocarcinoma
- Large Cell Carcinoma
- Squamous Cell Carcinoma
- Normal

---

## 📊 Model Performance

The evaluated classification models produced the following reported results:

| Model | Accuracy | Mean AUC |
|---|---:|---:|
| GoogLeNet | **91.75%** | **0.988** |
| ResNet-50 | **90.48%** | **0.984** |
| ResNet-101 | **90.16%** | **0.988** |

Among the evaluated models, **GoogLeNet achieved the highest reported classification accuracy of 91.75%**.

> Performance values are based on the experiments conducted for this project and may vary depending on dataset composition, preprocessing, training configuration, and evaluation methodology.

---

## 🔍 Explainable AI

A major component of PulmoScan.AI is **Grad-CAM visualization**.

Instead of displaying only:

```text
Prediction: Adenocarcinoma
Confidence: XX%
