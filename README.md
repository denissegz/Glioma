# Glioma Classification and Risk Analysis using Machine Learning

## Overview

This project focuses on glioma classification and survival risk analysis using machine learning (ML) models within Jupyter Notebooks. Gliomas are a type of brain tumor that pose significant challenges in medical diagnostics and treatment planning. The goal of this project is to integrate advanced machine learning techniques to classify glioma subtypes based on the 2021 WHO criteria and perform survival risk analysis to improve prognosis and treatment strategies. 

The repository includes Jupyter notebooks for both the classification and risk analysis models, as well as methods for extracting and preprocessing data from The Cancer Genome Atlas (TCGA). The project utilizes the Logistic Regression and Random Forest classifiers, along with Explainable Artificial Intelligence (XAI) techniques for feature importance analysis using SHAP values.

## Table of Contents

1. [Introduction](#introduction)
2. [Methodology](#methodology)
    - [Data Collection](#data-collection)
    - [Data Preprocessing](#data-preprocessing)
    - [Modeling](#modeling)
    - [Explainable AI](#explainable-ai)
    - [Risk Analysis](#risk-analysis)
3. [Results](#results)
    - [Classification Results](#classification-results)
    - [XAI Results](#xai-results)
    - [Risk Analysis Results](#risk-analysis-results)
4. [Discussion](#discussion)
5. [Conclusions](#conclusions)

## Introduction

Gliomas account for most primary brain tumors in adults and present a major challenge in neuro-oncology. This project leverages machine learning (ML) models to classify gliomas based on histopathological, genetic, and epigenetic data from TCGA, and performs survival risk analysis. The ultimate aim is to integrate classification with prognostic risk analysis to help clinicians in diagnosis and treatment planning.

## Methodology

### Data Collection

The dataset for this study is derived from The Cancer Genome Atlas (TCGA), containing clinical and DNA methylation data for glioma patients. The data includes clinical outcomes, such as overall survival (OS), disease-specific survival (DSS), and progression-free interval (PFI), as well as DNA methylation markers for approximately 11,160 patients with glioblastoma (GB) and low-grade glioma (LG) subtypes.

### Data Preprocessing

1. **Filtering**: Patients were filtered to include only those classified with glioblastoma (GB) or low-grade gliomas (LG), specifically astrocytoma and oligodendroglioma.
2. **Data Merging**: Clinical data was merged with genomic data based on patient ID.
3. **Missing Values**: Columns with more than 50 missing values were removed.
4. **Subtype Mapping**: Glioma subtypes were mapped to the following classes:
    - Astrocytoma: Class 0
    - Glioblastoma: Class 1
    - Oligodendroglioma: Class 2

### Modeling

Two machine learning models were used for glioma classification:
- **Logistic Regression**
- **Random Forest**

The dataset was divided into a training (80%) and testing (20%) set.

### Explainable AI

To understand the feature importance in the models, SHAP (Shapley Additive Explanations) values were calculated for both Logistic Regression and Random Forest models. SHAP values help identify the most influential features that impact model predictions.

### Risk Analysis

For survival risk analysis, three events were considered:
- Overall Survival (OS)
- Disease-Specific Survival (DSS)
- Progression-Free Interval (PFI)

The models used for risk analysis were:
- **Logistic Regression**
- **XGB Classifier**

## Results

### Classification Results

The classification accuracy for both Logistic Regression and Random Forest models was as follows:

| Class | Logistic Regression Accuracy | Random Forest Accuracy |
|-------|------------------------------|------------------------|
| Class 0 (Astrocytoma) | 1.00 | 0.98 |
| Class 1 (Glioblastoma) | 1.00 | 1.00 |
| Class 2 (Oligodendroglioma) | 0.97 | 0.97 |

### XAI Results

#### Logistic Regression (Top Features for Each Subtype)

- **Astrocytoma**: cg24597705, cg03909781, cg25594899, etc.
- **Glioblastoma**: cg25594899, cg27561954, cg03909781, etc.
- **Oligodendroglioma**: cg18115132, cg15814736, cg24189559, etc.

#### Random Forest (Top Features for Each Subtype)

- **Astrocytoma**: cg08765301, cg17737263, cg12978275, etc.
- **Glioblastoma**: cg16328207, cg14355794, cg26812852, etc.
- **Oligodendroglioma**: cg08765301, cg12978275, cg06967124, etc.

### Risk Analysis Results

The models performed well on survival events:

#### Overall Survival (OS)
- Logistic Regression: 0.989 (training), 0.991 (test)
- XGB Classifier: 0.989 (training), 0.991 (test)

#### Disease-Specific Survival (DSS)
- Logistic Regression: 0.998 (training), 1.000 (test)
- XGB Classifier: 0.987 (training), 1.000 (test)

#### Progression-Free Interval (PFI)
- Logistic Regression: 0.846 (training), 0.863 (test)
- XGB Classifier: 0.846 (training), 0.836 (test)

## Discussion

The results indicate that both Logistic Regression and Random Forest models are highly effective for glioma classification, with accuracies approaching 99% overall. The SHAP analysis revealed that certain DNA methylation markers are key in distinguishing glioma subtypes, providing insight into the molecular features relevant for diagnosis. 

For risk analysis, the models performed better for OS and DSS events compared to PFI, reflecting the complex nature of progression-free survival prediction.

## Conclusions

This study demonstrates that machine learning models can accurately classify glioma subtypes and predict survival outcomes, offering a promising approach for clinical decision-making and personalized treatment strategies. The integration of classification and survival risk analysis represents an important step toward improving glioma prognosis.

## Setup Instructions

### Prerequisites

To run the code, make sure you have the following dependencies installed:

- Python 3.x
- pandas
- numpy
- scikit-learn
- xgboost
- shap
- matplotlib
- seaborn
- jupyter



