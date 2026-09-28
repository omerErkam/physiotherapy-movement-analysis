# Physiotherapy Movement Analysis & Clinical Score Regression

![Poster](Buraya_Görseli_Sürükleyip_Bıraktığında_Otomatik_Link_Gelecek)<img width="4967" height="7021" alt="Academic Research Poster in Blue and White Contemp_260616_102947 (2) copy" src="https://github.com/user-attachments/assets/d3eb9270-a9d5-49ee-94fa-2796de550b84" />


> **Note:** This repository is currently transitioning from an academic research phase to a modular production pipeline. The main root contains the final, stable ST-GCN implementation. The `research_and_experiments` directory contains raw experimental notebooks, ablation studies, and baseline tests (including data leakage analysis and negative results) conducted during the thesis timeline.

## Overview
This project presents an end-to-end deep learning pipeline designed to automate the clinical assessment of physiotherapy exercises. Utilizing the KIMORE benchmark dataset, the system analyzes 3D skeletal motion data to validate clinical expertise, classify patient cohorts (Stroke, Back Pain, Parkinson's), and predict continuous clinical scores (0-50).

## Key Features & Contributions
* **Biomechanical Engineering:** Upgraded the standard 12-joint skeletal baseline to a 23-joint enhanced mesh using MediaPipe and OpenCV to capture nuanced peripheral kinematics.
* **Dual-Task Classification:** 
  * SVM-based model for Expert vs. Non-Expert validation (85.03% Accuracy, 0.8406 F1-Score).
  * Random Forest model for Patient Cohort Classification (70.00% Accuracy, 0.6616 F1-Score).
* **Clinical Score Regression (ST-GCN):** Developed a Spatio-Temporal Graph Convolutional Network (ST-GCN) achieving an RMSE of 7.75, MAE of 5.92, and Spearman $\rho=0.670$.
* **Robust Evaluation & Data Leakage Resolution:** Identified and corrected a subject-level data leakage flaw present in prior literature, migrating the evaluation pipeline to a strict 5-fold subject-disjoint GroupKFold cross-validation structure.

## Repository Structure
* `/02_Final_STGCN_Regression_Pipeline.ipynb`: The main, finalized pipeline containing data preprocessing, GroupKFold splits, and the trained regression models.
* `/research_and_experiments/`: Contains ablation studies, feature extraction logic, classification baselines, and historical tests demonstrating the iterative engineering process.
