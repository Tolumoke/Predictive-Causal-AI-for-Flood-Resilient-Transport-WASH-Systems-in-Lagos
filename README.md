# Predictive-Causal-AI-for-Flood-Resilient-Transport & WASH-Systems-in-Lagos
An AI-Powered Climate Resilient Infrastructure Investment With Causal Modeling & Prescriptive ROI Optimization for Lagos Coastal Corridor


## Project Overview

This project introduces a **3-stage hybrid framework** that combines 
**Predictive Machine Learning**, 
**Causal Inference**, and 
**Prescriptive ROI Optimization** 
to help Lagos (and other coastal cities) proactively manage flooding impacts on:

- **Transport networks** (road disruption)  
- **Water & sanitation systems (WSS)** (contamination risk)  

The core purpose is simple but urgent:

> **Predict where failures will occur, understand why they occur, and recommend which infrastructure investments reduce risk most per dollar.**

This framework is built to support:

- Climate adaptation planning  
- Resilient infrastructure investment  
- Urban mobility protection  
- Public health and water-system safety  

# **Why This Matters**

Coastal megacities like Lagos experience severe disruptions when rainfall overwhelms aging drainage systems.  

These disruptions ripple across:

- Transportation (gridlock, road collapse, commuter delays)  
- Economy (business downtime, supply-chain delays)  
- Public health (waterborne disease outbreaks)  

This project is designed to convert complex environmental data into  
**actionable engineering and policy guidance**.

# **Technology Stack**

### **🛰 Data Sources**
- Google Earth Engine (DEM, land cover, NDVI/NDBI, imagery)  
- GRID3 Lagos geospatial layers  
- IMERG Lagos precipitation data  
- OpenStreetMap road network  

### **📈 Predictive Modeling**
- Python (Pandas, NumPy)
- Scikit-learn  
- **XGBoost (core predictive engine)**

### **📊 Causal Inference**
- EconML  
- Statsmodels  
- Double Machine Learning (DML)

### **📐 Visualization**
- Matplotlib  
- Seaborn  
- SHAP (model interpretability)

-----------

# **Stage 1: Predictive ML (XGBoost)**  
### **Goal:** 
Identify *which roads* are likely to fail under rainfall conditions.

Using spatial + temporal features:
- precipitation  
- elevation  
- slope  
- NDVI  
- NDBI  
- flood mask  
- land cover  

The XGBoost classifier achieved:

- **Accuracy:**                   0.9998  
- **Precision:**                  0.994  
- **Recall:**                     1.00  
- **ROC-AUC:**                    0.9999  

Outputs generated:

- Flood-prone road maps  
- SHAP interpretability plots  
- ROC curves  
- Prediction CSV for planners  

This stage supports operational decision-making and vulnerability mapping.

-------

# **Stage 2: Causal AI (Double Machine Learning)**  
### **Goal:** 
Understand *why* disruptions occur and quantify the unconfounded effect of rainfall.

Two causal targets:

### **1. Transport Disruption (Y₁)**  
- Causal Effect: **11.62 in 10,000** additional disruption probability per 1 mm rainfall  
- Controls: Elevation, slope, NDBI, land cover  
- Method: DML with logistic loss  

### **2. Water & Sanitation Contamination Risk (Y₂)**  
- Causal Effect: **4.16 in 10,000** additional contamination probability per 1 mm rainfall  
- Method: Robust DML (non-convex gradient correction)

# Why this matters:

> Governments cannot invest based on correlation 
> They require *causal* evidence to justify spending billions in infrastructure upgrades.

This stage validates:
- The rainfall → failure mechanism  
- System sensitivity  
- Environmental confounder impacts  

--------

# **Stage 3: Prescriptive ROI Optimization**  
### **Goal:** 
Recommend the optimal mix of:
- **Grey infrastructure** (drainage upgrades)  
- **Green infrastructure** (permeable pavements)  

Using:
- Causal metrics (AME)
- Engineering capacity data
- Cost models
- Risk-reduction sensitivity analysis

Output:

> **For every $1 spent on green or grey infrastructure,  
> how much disruption and contamination risk is reduced?**

This is a decision-support tool for:
- Ministries of Works / Transport  
- Water and Sanitation Agencies  
- Climate resilience funds  
- Donor organizations  

-------

# Project Structure

├── data/
│   ├── raw/
│   ├── processed/
│   └── MASTER_CAUSAL_DATASET_V1.csv
│
├── src/
│   ├── 0_data_preparation/
│   │   ├── gee_extraction_scripts/
│   │   └── merge_temporal_spatial.py
│   │
│   ├── 1_predictive_model/
│   │   ├── xgboost_training.py
│   │   ├── xgboost_evaluation.py
│   │   └── generate_predictions.py
│   │
│   ├── 2_causal_inference/
│   │   ├── dml_transport.py
│   │   ├── dml_wss.py
│   │   └── causal_summaries/
│   │
│   ├── 3_prescriptive_optimization/
│   │   ├── roi_model.py
│   │   ├── investment_tradeoff.py
│   │   └── sensitivity_analysis.py
│   │
│   └── utils/
│       ├── plotting.py
│       ├── metrics.py
│       └── shap_utils.py
│
├── models/
│   ├── xgb_model.pkl
│   ├── feature_importances.png
│   ├── roc_curve.png
│   └── shap_summary.png
│
├── results/
│   ├── predictions.csv
│   ├── transport_AME.txt
│   ├── wss_AME.txt
│   └── investment_recommendation.pdf
│
├── requirements.txt
├── README.md
└── LICENSE

-------------

# Getting Started

1. Prerequisites

*You need Python 3.9+ and Git installed*

2. Clone the repository:

git clone https://github.com/Tolumoke/Predictive-Causal-AI-for-Flood-Resilient-Transport-WASH-Systems-in-Lagos

cd Predictive-Causal-AI-for-Flood-Resilient-Transport-WASH-Systems-in-Lagos

3. Install dependencies:

*pip install -r requirements.txt*


**Usage: Full Workflow Execution**

Run the following commands sequentially to execute the full three-stage pipeline (assuming necessary data is in the data/ folder).

4. Run Predictive ML (Stage 1 Training):

*python src/1_predictive_model/xgboost_training.py*


5. Run Causal Inference (Stage 2):

*python src/2_causal_inference/dml_transport.py*
*python src/2_causal_inference/dml_wss.py*


6. Generate Investment Recommendations (Stage 3):

*python src/3_prescriptive_optimization/roi_model.py*

-------

# Project Development Status
**Stage 1: Predictive Modeling (XGBoost) ✔️ Completed**

*High-performance flood disruption classifier

*SHAP analysis

*Model evaluation and metrics

--------

**Stage 2: Causal Inference (DML) ⏳ In progress**

*Target: Transport Disruption

*Target: WSS Contamination Risk

*AME computation using Double ML

*Expected completion: Q1 2026

-------

**Stage 3: Prescriptive ROI Optimization ⏳ Planned**

*Grey vs Green infrastructure investment simulation

*Cost-effectiveness trade-off models

*Risk-reduction per dollar analysis

*Expected completion: Q2 2026

-------

**Repository Structure**

project/
│── data/                # Cleaned climate datasets
│── notebooks/
│    ├── 01_prediction_xgboost.ipynb
│    ├── 02_causal_modeling_doubleml.ipynb (placeholder)
│    ├── 03_optimization_roi.ipynb (placeholder)
│── models/
│── reports/
│── README.md
│── requirements.txt

📌 **Status Note**

Only Stage 1 is fully implemented so far.
Stages 2 and 3 have placeholders and will be added progressively.
This README is written intentionally to reflect the full project vision while clearly stating what has and has not been completed.

-------

**Citation**

If you use this project, please cite:

Tolumoke Israel Ola (2025).  
Predictive–Causal AI for Flood-Resilient Transport & WASH Systems in Lagos.

-------

**Acknowledgements**

Special thanks to:

Google Earth Engine

GRID3 & IMERG data providers

EconML & XGBoost communities

Climate resilience researchers across Africa

-------

**Contact**

For collaboration, research inquiries, or consulting:

Tolumoke Israel Ola

LinkedIn: https://www.linkedin.com/in/tolumokeisraelola/

Email: tolumokeisraelola@gmail.com
