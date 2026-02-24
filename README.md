#  Data Generation using Modelling & Simulation for Machine Learning  
##  Multi-Criteria Model Selection using TOPSIS

---

##  Abstract

This project demonstrates a complete pipeline for **synthetic data generation using modelling and simulation**, followed by **machine learning regression** and **multi-criteria model selection**.

Instead of selecting the best model using a single evaluation metric, a **Multi-Criteria Decision Making (MCDM)** technique — **TOPSIS (Technique for Order Preference by Similarity to Ideal Solution)** — is applied to rank models scientifically using multiple performance criteria.

The project integrates:

- Discrete-event simulation (SimPy)  
- Synthetic data generation  
- Machine learning regression models  
- Multi-criteria decision analysis (TOPSIS)  

This approach ensures robust, unbiased, and well-justified model selection.

---

## 1️ Problem Statement

Collecting large-scale system performance data is often expensive or impractical.  
Simulation-based modelling allows controlled and reproducible synthetic dataset generation.

However, selecting a machine learning model using only a single metric (e.g., R²) may lead to biased conclusions.

### Project Objectives

- Generate **1000 simulation samples**
- Train multiple regression models
- Evaluate using multiple performance metrics
- Apply **TOPSIS** for scientific ranking

---

## 2️ Simulation Tool

### SimPy – Discrete Event Simulation (Python)

**Why SimPy?**

- Open-source
- Python-based
- Suitable for queueing systems
- Lightweight and Colab-compatible
- Widely used in operations research

---

## 3️ Methodology

### 🔹 Step 1: Simulation Data Generation

A queueing system is simulated using SimPy.

The system models:

- Customer arrivals
- Service processing
- Waiting time accumulation

---

### 🔹 Simulation Parameters

| Parameter | Description |
|------------|-------------|
| Arrival Rate (λ) | Rate of customer arrival |
| Service Rate (μ) | Service processing rate |
| Servers | Number of parallel servers |
| Simulation Time | Total run time |

---

### 🔹 Parameter Ranges

| Parameter | Range |
|------------|--------|
| Arrival Rate | 0.5 – 5.0 |
| Service Rate | 1.0 – 10.0 |
| Servers | 1 – 3 |
| Simulation Time | 50 – 200 |

---

### 🔹 Dataset Structure

| arrival_rate | service_rate | servers | sim_time | avg_wait_time |

The **average waiting time** is the target variable.

---

## 4️ Machine Learning Models

The following models were trained:

1. Linear Regression  
2. Ridge Regression  
3. Lasso Regression  
4. Decision Tree  
5. Random Forest  
6. Gradient Boosting  
7. K-Nearest Neighbors (KNN)  

### Dataset Split
- 80% Training
- 20% Testing

---

## 5️ Evaluation Metrics

Each model was evaluated using:

| Metric | Type |
|--------|--------|
| MSE | Minimize |
| MAE | Minimize |
| RMSE | Minimize |
| R² | Maximize |
| Training Time | Minimize |

---

## 6️ TOPSIS Ranking

TOPSIS ranks models based on distance from:

- Ideal Best Solution
- Ideal Worst Solution

### Criteria Weights

| Metric | Weight | Objective |
|--------|--------|------------|
| MSE | 0.20 | Minimize |
| MAE | 0.15 | Minimize |
| RMSE | 0.20 | Minimize |
| R² | 0.35 | Maximize |
| Training Time | 0.10 | Minimize |

---

## 7️ Results

### 🔹 Model Performance

| Model | MSE | MAE | RMSE | R² | Train Time (s) |
|-------|------|------|------|------|----------------|
| Linear Regression | 25.70 | 3.29 | 5.07 | 0.25 | 0.0065 |
| Ridge Regression | 25.70 | 3.29 | 5.07 | 0.25 | 0.0077 |
| Lasso Regression | 26.98 | 2.94 | 5.19 | 0.22 | 0.0031 |
| Decision Tree | 15.25 | 1.00 | 3.91 | 0.56 | 0.0088 |
| **Random Forest** | **4.97** | **0.69** | **2.23** | **0.86** | **0.72** |
| Gradient Boosting | 11.78 | 1.37 | 3.43 | 0.66 | 0.32 |
| KNN | 24.02 | 1.74 | 4.90 | 0.30 | 0.0029 |

---

### 🔹 TOPSIS Ranking

| Rank | Model | TOPSIS Score |
|------|--------|--------------|
| 1 | Random Forest | 0.6925 |
| 2 | Gradient Boosting | 0.6655 |
| 3 | Decision Tree | 0.6147 |
| 4 | KNN | 0.3739 |
| 5 | Linear Regression | 0.3194 |
| 6 | Ridge Regression | 0.3191 |
| 7 | Lasso Regression | 0.3110 |

---
<img width="1618" height="931" alt="image" src="https://github.com/user-attachments/assets/1fa82b8f-5cfa-40c5-b8e4-15d3ef76c02c" />

##  Best Model

**Random Forest** achieved the highest TOPSIS score (0.6925), indicating the best balance between accuracy, error minimization, and computational efficiency.

---

## 📁 Project Structure
