# YOLO_Robot_Suitability_Score

A comparative study of state-of-the-art YOLO models for **indoor robot perception** using a novel **Robot Suitability Score** framework.

---

## 📌 Overview

This project evaluates **YOLO26**, **YOLO11**, and **YOLOv8** (nano variants) for robotic applications by proposing a **multi-criteria Robot Suitability Score**. The framework considers four key factors essential for real-world robot deployment:

- Detection Accuracy
- Inference Speed
- Quantization Robustness
- Resource Efficiency

The evaluation is performed on the **HomeObjects-3K** dataset, which contains indoor objects relevant to robot navigation.

---

## 🎯 Motivation

Most existing benchmarks for object detection models focus only on accuracy (mAP). However, deploying models on real robots requires balancing multiple factors such as speed, quantization performance (for edge devices), and model size.

This project introduces a **weighted Robot Suitability Score** to provide a more practical evaluation for robotics and TinyML applications.

---

## 🧠 Robot Suitability Score

The final score is calculated as:

$$
\text{Robot Suitability Score} = 0.35 \times \text{Norm(mAP)} + 0.25 \times \text{Norm(FPS)} + 0.25 \times \text{Quantization Robustness} + 0.15 \times \text{Norm(Size Efficiency)}
$$

---

## 📊 Models Evaluated

| Model     | Type              | Strengths                          |
|-----------|-------------------|------------------------------------|
| **YOLO26**    | Latest Generation | Best quantization robustness       |
| **YOLO11**    | Previous Generation | Highest overall suitability score |
| **YOLOv8**    | Established Baseline | Fastest inference speed         |

---

## 📁 Dataset

- **Name**: HomeObjects-3K
- **Description**: Indoor object detection dataset with 12 classes
- **Relevance**: Suitable for robot navigation in indoor environments

---

## 📈 Results

| Rank | Model   | mAP50-95 | FPS    | Robot Suitability Score |
|------|---------|----------|--------|--------------------------|
| 1    | YOLO11  | 0.4740   | 513.9  | **0.8078**               |
| 2    | YOLO26  | 0.4529   | 416.9  | 0.7970                   |
| 3    | YOLOv8  | 0.3981   | 1336.2 | 0.7487                   |

**Key Insights**:
- YOLO11 achieved the highest overall suitability score.
- YOLO26 showed the best quantization robustness.
- Both newer models significantly outperformed YOLOv8 in detection accuracy.

---

## 📊 Visualizations

The repository includes the following figures:

- **Pareto Front**: Accuracy vs Real-time Latency
- **Line Plot**: Normalized performance across key factors
- **Bar Chart**: Robot Suitability Score comparison
- **Radar Chart**: Multi-dimensional model profile

---

## 🛠️ Technologies Used

- Ultralytics YOLO
- PyTorch
- Matplotlib & Seaborn
- Pandas & NumPy

---
