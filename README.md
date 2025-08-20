# Interpreting Time-Series Forecasts with LIME & SHAP
*Case Study: Air Passengers Dataset*

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)  
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)  
[![scikit-learn](https://img.shields.io/badge/ML-ScikitLearn-green.svg)](https://scikit-learn.org/stable/)  
[![statsmodels](https://img.shields.io/badge/Stats-Statsmodels-blue.svg)](https://www.statsmodels.org/)  
[![xgboost](https://img.shields.io/badge/Boosting-XGBoost-red.svg)](https://xgboost.readthedocs.io/)  
[![SHAP](https://img.shields.io/badge/Explainability-SHAP-brightgreen.svg)](https://shap.readthedocs.io/)  
[![LIME](https://img.shields.io/badge/Explainability-LIME-yellow.svg)](https://github.com/marcotcr/lime)  

---

## 📌 Overview
- This project reproduces the experiments and figures from the accompanying paper on **interpretable time-series forecasting**.  
- We use the **AirPassengers dataset (1949–1960)** and compare **ARIMA** with a **feature-based machine learning model** (XGBoost or RandomForest).  
- Interpretability is added through **LIME** and **SHAP**, with plots and tables numbered exactly as in the paper.

---

## 📂 Repository Structure
```
.
├── timeseries_interpretation_lime_shap.ipynb   # Main annotated notebook
├── Data/
│   └── AirPassengers.csv                                    # Source dataset
├── Figures/
│   ├── Figure_1.png                                         # Forecast comparison
│   ├── Figure_2.png                                         # SHAP global importance
│   ├── Figure_3.png                                         # SHAP dependence
│   ├── Figure_4.png                                         # LIME local explanation
│   └── Figure_5.png                                         # Permutation importance
├── requirements.txt                                         # Dependencies
└── README.md                                                # Project documentation
```

---

## ⚙️ Setup & Installation
Clone the repository and install dependencies:

```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>

# Create a virtual environment (optional but recommended)
python -m venv venv
source venv/bin/activate   # (Linux/Mac)
venv\Scripts\activate      # (Windows)

# Install requirements
pip install -r requirements.txt
```

**Dependencies (requirements.txt):**
- pandas  
- numpy  
- matplotlib  
- scikit-learn  
- statsmodels  
- xgboost  
- shap  
- lime  

---

## 🚀 Usage
Open the notebook:

```bash
jupyter notebook timeseries_interpretation_lime_shap.ipynb
```

Run all cells to:
1. Load and preprocess the AirPassengers dataset.  
2. Train ARIMA (classical baseline) and XGBoost/RandomForest models.  
3. Generate Figures 1–5 and Tables 1–3 from the paper:
   - Figure 1: Forecast comparison (1959–1960).  
   - Figure 2: SHAP global importance (mean |value|).  
   - Figure 3: SHAP dependence for `Lag_12` (color=`Lag_1`).  
   - Figure 4: LIME local explanation for July 1959.  
   - Figure 5: Permutation feature importance.  

All plots are automatically saved as `.png` files in the working directory.

---

## 📊 Results (from Paper)
- **ARIMA** provides a strong seasonal baseline.  
- **XGBoost/RandomForest** with lagged features and seasonality encodings achieves lower RMSE and MAPE.  

**Interpretability Highlights:**
- `Lag_12` dominates due to yearly seasonality.  
- **LIME** shows local feature influence for specific months.  
- **SHAP** explains both global and local contributions, complementing LIME.  

---

## 📖 Paper

This repository accompanies the following preprints:

- [📰 arXiv:2508.12253 – Interpreting Time-Series Forecasts with LIME and SHAP: AirPassengers Case Study](https://arxiv.org/abs/2508.12253)  
- [📑 Research Square – Interpreting Time-Series Forecasts with LIME and SHAP](https://www.researchsquare.com/article/rs-7358158/v1)  


---

## 📝 Citation
If you use this notebook in your research or teaching, please cite:

```
@software{shukla2025timeserieslimeShap,
  author       = {Shukla, Manish A.},
  title        = {Time-Series-Interpretation-Lime-Shap},
  year         = {2025},
  publisher    = {Zenodo},
  doi          = {10.5281/zenodo.16906228},
  url          = {https://doi.org/10.5281/zenodo.16906228}
}

@article{shukla2025airlime,
  title={Interpreting Time-Series Forecasts with LIME and SHAP: AirPassengers Case Study},
  author={Manish A. Shukla},
  year={2025},
  eprint={2508.12253},
  archivePrefix={arXiv},
  primaryClass={cs.LG}
}

@article{shukla2025preprint,
  title={Interpreting Time-Series Forecasts with LIME and SHAP},
  author={Manish A. Shukla},
  journal={Research Square},
  year={2025},
  note={Preprint}
}


```

---

## 🤝 Contributing
Pull requests are welcome! For major changes, please open an issue first to discuss what you’d like to add.

---

## 📧 Contact
- **Author**: Manish A. Shukla  
- **Email**: manishshukla.ms18@gmail.com  
- **LinkedIn**: [linkedin.com/in/manishshukla-ms](https://www.linkedin.com/in/manishshukla-ms)  
- **Website**: [manishshukla.com](https://www.manishshukla.com)  
