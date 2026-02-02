# Credit Risk Classification and Explainable AI (XAI) – Bachelor Thesis

This repository contains the public, reproducible part of my Bachelor Thesis:  
**“Classification and Explainability (XAI) in Credit Risk: Black-Box vs Interpretable Models”**, developed at Universidad de Sevilla.

> All data in this repository is synthetic or public. Real institutional data and some sensitive implementation details are not included.

---

## 1. Project Overview

The goal of this thesis is to compare traditional and machine learning models for credit risk scoring and to evaluate them not only by predictive performance, but also by:

- Statistical robustness (Monte Carlo validation and confidence intervals)
- Economic impact (loss functions with different costs for FP vs FN)
- Explainability (global & local XAI)
- Basic fairness analysis between groups when possible

---

## 2. Main Components

- **Datasets (synthetic/public replicas)**  
  Inspired by:
  - German Credit (consumer loans)
  - HELOC (home equity line of credit)
  - Home Credit–like dataset (large retail lending)

- **Models**
  - Logistic Regression (benchmark)
  - Decision Trees
  - Random Forest
  - Gradient Boosting
  - (Optional) Stacking / hybrid model

- **Evaluation**
  - ROC curves, AUROC, Gini
  - F1, precision, recall at different thresholds
  - Monte Carlo repeated validation to quantify uncertainty

- **XAI**
  - Global importance analysis (e.g. SHAP)
  - Local explanations for individual clients (e.g. LIME)
  - Link from explanations to business rules and credit policies

- **Fairness (high level)**
  - Basic comparison of approval rates and errors between groups
  - Discussion of efficiency–equity trade-offs

---

## 3. Repository Structure

```text
notebooks/
  01_eda_datasets.ipynb           # exploratory analysis
  02_baseline_models.ipynb        # LR, trees, RF, GB
  03_monte_carlo_validation.ipynb # robustness & confidence intervals
  04_xai_shap_lime.ipynb          # global & local explanations
  05_fairness_overview.ipynb      # simple fairness metrics (optional)

src/
  data_preprocessing.py  # cleaning, encoding, train/test split
  modeling.py            # model definitions & training
  evaluation.py          # metrics, ROC, loss functions
  xai_utils.py           # SHAP / LIME helpers

data/
  synthetic/             # synthetic sample datasets
  README.md              # describes schema & source

reports/
  thesis_defense.pdf  # summary of the thesis for recruiters

environment.yml / requirements.txt
LICENSE
.gitignore

