---
title: "Interpreting Time-Series Forecasts with LIME & SHAP"
tags:
  - Python
  - time series
  - interpretability
  - SHAP
  - LIME
authors:
  - name: Manish A. Shukla
    affiliation: 1
    orcid: https://orcid.org/0009-0005-1093-5816
affiliations:
  - name: Independent Researcher
    index: 1
date: 20 August 2025
bibliography: paper.bib
---

# Summary

`ts-interpret` (repository: https://github.com/Manishms18/Time-Series-Interpretation-Lime-Shap) provides a reproducible toolkit for interpreting univariate time-series forecasts using both statistical and machine-learning models. It integrates **ARIMA** and **XGBoost** forecasting with **SHAP** and **LIME** explanations to enable global feature importance and local interpretability. 

The software is demonstrated on the canonical *AirPassengers* dataset but generalizes to other seasonal univariate series. By packaging common tasks—lag feature generation, baseline model fitting, boosting-based forecasting, and post-hoc explanations—`ts-interpret` lowers the barrier for practitioners and researchers to obtain interpretable insights from forecasting pipelines.

# Statement of need

Time-series forecasting is a central task in applied domains such as economics, operations, and climate science. While black-box models such as boosted trees often achieve high predictive accuracy, their opacity hinders adoption in domains requiring **trust and accountability**. Although generic toolkits like **SHAP** and **LIME** exist, they are not directly tailored to time-series workflows.

`ts-interpret` fills this gap by:
- Providing lightweight utilities for **lagged feature engineering** on time-indexed data.
- Wrapping **ARIMA** (as a statistical baseline) and **XGBoost** (as a non-linear learner) in simple functions.
- Exposing **interpretability functions** for both global (feature importance) and local (case-specific) explanations.
- Demonstrating the full workflow in a reproducible notebook.

This package aims to assist researchers and applied practitioners who need interpretable forecasts but prefer lightweight, transparent code rather than large frameworks.

# State of the field

- **ARIMA** remains a strong statistical baseline for seasonal series [@boxjenkins].  
- **XGBoost** [@chen2016xgboost] and other machine-learning methods often outperform linear models but are harder to interpret.  
- **SHAP** [@lundberg2017shap] and **LIME** [@ribeiro2016lime] are general post-hoc explanation methods, but lack ready-to-use wrappers for time-series forecasting contexts.  
- Supporting tools like **scikit-learn** [@pedregosa2011sklearn] and **statsmodels** [@seabold2010statsmodels] provide modeling utilities, but not integrated interpretability for temporal features.

`ts-interpret` contributes a **bridge**: small, research-friendly software that unifies forecasting and explanation for lag-based time-series, with reproducible examples.

# Usage

The library exposes:
- `load_airpassengers()` – load sample data.  
- `make_lag_features()` – generate lagged predictors.  
- `fit_arima()` – statistical baseline model.  
- `fit_xgboost()` – machine-learning model.  
- `forecast()` – unified forecasting interface.  
- `shap_global_importance()` – compute average SHAP importances.  
- `lime_local_explanation()` – explain individual predictions with LIME.  

A worked notebook provides step-by-step usage and visualizations.

# Acknowledgements

The author thanks the open-source community for tools such as SHAP, LIME, statsmodels, scikit-learn, and XGBoost.  
