# 🛡️ Density and Risk Assessment Based on Mobile Sensing Technology

This project leverages data from multiple sensors to classify human activities into **danger levels** ranging from 1 (lowest) to 7 (highest). The model is trained using features extracted from **sensor logs**, **audio data**, and **aerial data**.

---

## 📁 Data Overview

### ✅ Collected Data Types

- **Sensor Logs**
  - Acceleration in the x-axis
  - Acceleration in the y-axis
  - Acceleration in the z-axis
  - Relative altitude
  - Pressure
  - Acceleration magnitude (calculated)

- **Audio**
  - MFCCs (Mel-Frequency Cepstral Coefficients)
  - Root Mean Square Energy
  - Spectral Centroid
  - Zero Crossing Rate

- **Aerial Data**
  - Average temperature
  - Average people count

All data is **organized, labeled**, and **aggregated** into a single `.csv` file for model training.

---

## 🧪 Feature Engineering

All features are extracted from the raw data and aggregated over time windows to form structured instances in the dataset.

- Feature extraction completed ✅
- Aggregated CSV file ready for training ✅

---

## ⚠️ Danger Level Definition

Each sample in the dataset is assigned a **danger level label** from 1 to 7, based on the type of human activity:

| Danger Level | Activity Description            |
|--------------|---------------------------------|
| 1            | walking                         |
| 2            | running                         |
| 3            | play_basketball_alone           |
| 4            | walking_at_7_floor              |
| 5            | play_basketball_with_kid        |
| 6            | walking_while_using_iphone      |
| 7            | danger_running                  |

---

## 🤖 Model Training

A machine learning model is trained to classify the danger level using either:

- **Random Forest**
- **XGBoost**

### Pipeline

1. Load the CSV file
2. Preprocess data
3. Split into training and test sets
4. Train the classifier
5. Evaluate performance (accuracy, confusion matrix)

