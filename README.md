# NASA Turbofan Jet Engine

This repository contains the work for the "Advanced Data Analysis and Machine Learning" research project at LUT University, Lappeenranta (FI). The project focuses on developing interpretable data-driven models for predictive maintenance of turbofan jet engines, using the NASA C-MAPSS datasets.

The goal is to build a monitoring framework that detects early signs of engine degradation through multivariate statistical process control, ensuring accurate and interpretable fault detection


## 🎯 About The Project

Modern aircraft engines generate high-dimensional sensor data that reflect their operational health.
Timely identification of deviations from normal behavior is crucial to anticipate failures and optimize maintenance.

This project implements a data-driven degradation monitoring framework based on Principal Component Analysis (PCA) and Kernel PCA (KPCA), combined with Multivariate Statistical Process Control (MSPC) using Hotelling’s T² and Q (SPE) statistics.

The system models healthy engine conditions and signals potential faults 10–20 cycles before failure.

## 🛠️ Methodology

We designed a three-stage framework for monitoring engine degradation:
1.  **Data preprocessing:** computation of Remaining Useful Life (RUL) labels, removal of constant variables, Z-score normalization for comparability across sensors
2.  **Dimensionality reduction with PCA and KPCA:**  PCA captures linear correlations and dominant degradation patterns among sensors. Its nonlinear extension Kernel PCA employs an RBF kernel to model more complex sensor relationships.
3.  **Statistical Process Monitoring:** construction of Hotelling’s T² and Q (SPE) control charts, calibration on healthy data (first 30% of cycles), validation on held-out engine subsets, performance metrics: True Positive Rate (TPR), False Alarm Rate (FAR), Detection Lead Time (DLT).

The code for data preprocessing, model implementation, and evaluation can be found in the `code/` directory.

## 📁 Repository Structure

The repository is organized as follows to ensure clarity and reproducibility:
 ```
NASA_Turbofan_Jet_Engine/
├── data/
│   ├── train_FD001.txt
│   ├── test_FD001.txt
│   ├── RUL_FD001.txt
│   └── ... (FD002–FD004)
├── code/
│   ├── project_pretreatment.m
│   ├── project_calibration.m
|   ├── project_calibration-kpca.m
│   ├── project_validation.m
|   ├── project_validation-kpca.m
│   ├── project_testing.m
|   ├── project_testing-kpca.m
├── REPORT.pdf
└── README.md
```
⚠️ **Note:** The original NASA C-MAPSS datasets are provided as a compressed archive (datasets.zip).
Due to file size, GitHub does not display the archive online, but it can be downloaded directly from the repository.

## ⚙️ Installation

To set up your environment and run this project, please follow these steps:

1.  Clone the repository:
    ```git clone https://github.com/alessiatani02/NASA-Turbofan-Engine-Monitoring.git cd NASA-Turbofan-Engine-Monitoring```

2. Open the project in MATLAB (version R2023b or later).
Make sure that the Statistics and Machine Learning Toolbox is installed.

## ▶️ Usage

The MATLAB scripts in the code/ directory provide a complete workflow for the project — from data pretreatment to model testing.
You can run them sequentially in MATLAB to reproduce the results presented in the report.

## 🧑‍💻 Contributors

* Alessia Tani
* Iiro Vendelin
* Sara Zambetti

Project tutored by Dr. Sabrina Duma.
