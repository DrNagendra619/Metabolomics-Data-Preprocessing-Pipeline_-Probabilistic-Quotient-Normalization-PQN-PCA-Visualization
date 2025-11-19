# Metabolomics-Data-Preprocessing-Pipeline_-Probabilistic-Quotient-Normalization-PQN-PCA-Visualization
Metabolomics Data Preprocessing Pipeline_ Probabilistic Quotient Normalization (PQN) and PCA Visualization
# Metabolomics Data Preprocessing Pipeline: PQN and PCA Visualization

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)
![Scikit-Learn](https://img.shields.io/badge/Library-Scikit--Learn-green)

## 📌 Overview
This repository contains a specialized Python workflow for processing simulated **Metabolomics intensity matrix data**. The pipeline is crucial for handling common issues in LC-MS metabolomics, such as variable sample dilution and missing values. It emphasizes the use of **Probabilistic Quotient Normalization (PQN)** and concludes with **Principal Component Analysis (PCA)** for visual structure discovery.

This project is suitable for demonstrating expertise in quantitative metabolomics data preparation.

## 🚀 Key Features
* **Data Simulation:** Generates synthetic metabolomics datasets mimicking LC-MS intensities ($200 \times 8$ matrix).
* **Realistic Noise Injection:** Simulates common issues like low-concentration metabolites or ionization failure by introducing 15% missing values.
* **Advanced Imputation:** Uses **K-Nearest Neighbors (KNN)** (k=5) to estimate missing data points based on similar metabolite profiles.
* **Specialized Normalization:** Implements **Probabilistic Quotient Normalization (PQN)**, widely used to correct for sample dilution, especially in urine metabolomics.
* **Dimensionality Reduction:** Applies **PCA** to reduce noise and visualize sample relationships in 2D space.

## 🛠️ Technologies Used
* **Python** (Core data processing)
* **NumPy** (Numerical operations)
* **Pandas** (Dataframe manipulation)
* **Scikit-Learn** (KNN Imputation, StandardScaler, PCA)
* **Matplotlib** (Data visualization)

## 📂 Workflow Description

The pipeline simulates a full metabolomics processing workflow:

1.  **Simulation & Missingness**: Creates a dataset of 200 metabolites across 8 samples, followed by the introduction of 15% random missing values.
2.  **Imputation**: Applies `KNNImputer (k=5)` to fill missing intensities.
3.  **Transformation**: The imputed data undergoes a **Log2 transformation** ($log_2(x+1)$) to stabilize variance and normalize the distribution.
4.  **Normalization (PQN)**: The data is normalized using PQN to correct for concentration differences (e.g., dilution factors) between samples.
5.  **Scaling**: The normalized data is scaled using `StandardScaler` to ensure all metabolites contribute equally to the PCA.
6.  **PCA Visualization**: PCA reduces the high-dimensional data to two Principal Components (PC1 and PC2) for visual analysis of sample clustering and overall variability.

## 📊 Interpreting the PCA Results

The final scatter plot visualizes the overall structure and relationships among your 8 samples:

* **Proximity indicates Similarity**: Samples located close together share similar metabolomic profiles after processing.
* **PC1 & PC2**: These axes capture the largest and second largest amounts of variance in the entire dataset, respectively.
* **Outlier Detection**: Points far from the main cluster(s) may represent outliers, suggesting unique biological or technical profiles.

## 🔧 Getting Started

### Prerequisites
Ensure you have Python installed along with the following libraries:

```bash
pip install numpy pandas scikit-learn matplotlib notebook
