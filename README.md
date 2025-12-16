# 🛡️ Density and Risk Assessment Based on Mobile Sensing Technology

This project explores a **multimodal risk assessment system** that leverages mobile sensing and aerial data to classify human activities into **danger levels ranging from 1 (lowest risk) to 7 (highest risk)**. By fusing sensor logs, audio signals, and aerial observations, the system demonstrates how low-cost, widely available devices (smartphones and drones) can support **context-aware safety monitoring** in urban and campus environments.

---

## 📌 Project Overview

The system integrates data collected from:

* **Mobile phones** (motion, altitude, pressure, audio)
* **Aerial platforms (drones)** (crowd density, people count, temperature)

Using feature engineering and ensemble machine learning models, the project classifies human activities into predefined danger levels that reflect increasing environmental and behavioral risk.

---

## 📁 Data Overview

### ✅ Collected Data Types

#### 📱 Sensor Logs (Mobile Devices)

* Acceleration (x-axis)
* Acceleration (y-axis)
* Acceleration (z-axis)
* Acceleration magnitude (calculated)
* Relative altitude
* Atmospheric pressure

#### 🔊 Audio Data

* MFCCs (Mel-Frequency Cepstral Coefficients)
* Root Mean Square (RMS) energy
* Spectral centroid
* Zero Crossing Rate

#### 🚁 Aerial Data (Drone)

* Average surface temperature (thermal imaging)
* Average people count
* Crowd density estimates

All modalities are **time-aligned, labeled, and aggregated** into a unified dataset. The final output is a **single CSV file** used for model training and evaluation.

---

## 🧪 Feature Engineering

Raw data streams are segmented into fixed-size time windows and transformed into structured features suitable for machine learning.

* Feature extraction completed ✅
* Multimodal feature fusion completed ✅
* Aggregated CSV file ready for training ✅

---

## ⚠️ Danger Level Definition

Each data sample is labeled with a **danger level (1–7)** based on the observed activity:

| Danger Level | Activity Description       |
| ------------ | -------------------------- |
| 1            | Walking                    |
| 2            | Running                    |
| 3            | Play basketball alone      |
| 4            | Walking at 7th floor       |
| 5            | Play basketball with kid   |
| 6            | Walking while using iPhone |
| 7            | Danger running             |

These labels represent increasing combinations of **density, kinetic energy, and behavioral risk**.

---

## 🤖 Model Training

The danger-level classification task is modeled as a **7-class supervised learning problem**.

### Models Used

* **Random Forest**
* **XGBoost**

### Training Pipeline

1. Load aggregated CSV dataset
2. Preprocess and normalize features
3. Split data into training and test sets (stratified)
4. Train ensemble classifier
5. Evaluate performance using:

   * Accuracy
   * Confusion matrix
   * Precision / Recall / F1-score

Both Random Forest and XGBoost achieved **perfect accuracy (1.00)** on the balanced test set, demonstrating strong discriminative power of the engineered features.

---

## 📊 Experimental Highlights

* Multimodal sensor fusion significantly improves risk classification
* Ensemble models perform exceptionally well on engineered features
* Leave-One-Activity-Out evaluation reveals opportunities for improving generalization

---

## 🛠️ Platform & Tools

* **Python**
* **Scikit-learn**
* **XGBoost**
* **Google Colab** (model training)

---

## 🔮 Future Work

* Real-time, on-device inference (mobile & drone edge deployment)
* Deep learning-based people counting (YOLO / Mask R-CNN)
* Continuous or probabilistic risk scoring
* Larger, more diverse datasets across environments and populations
* Human-in-the-loop feedback for adaptive risk assessment

---

## 📄 Authors

* Micheal Lai
* Uchechukwu Uboh
* Joshua Hill

---

## 📌 Summary

This project demonstrates the feasibility of **mobile and aerial sensing combined with ensemble learning** for accurate, context-aware danger assessment. The approach highlights a scalable foundation for smart campus safety, crowd monitoring, and urban risk management systems.
