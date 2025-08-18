# Interpreting Time-Series Forecasts with LIME & SHAP
*Case Study: AirPassengers Dataset*

## Overview
- This project reproduces the experiments and figures from the accompanying paper on **interpretable time-series forecasting**.  
- We use the **AirPassengers dataset (1949–1960)** and compare **ARIMA** with a **feature-based machine learning model** (XGBoost or RandomForest).  
- Interpretability is added through **LIME** and **SHAP**, with plots and tables numbered exactly as in the paper.

## Repository Structure
```
.
├── airpassengers_lime_shap_paper_style_v2_annotated.ipynb   # Main annotated notebook
├── Data/
│   └── AirPassengers.csv                                    # Source dataset
├── Figures/
│   ├── Figure_1.png                                         # Forecast comparison
│   ├── Figure_2.png                                         # SHAP global importance
│   ├── Figure_3.png                                         # SHAP dependence
│   ├── Figure_4.png                                         # LIME local explanation
│   └── Figure_5.png                                         # Permutation importance
└── README.md                                                # Project documentation
```

## Setup & Installation
Clone the repository and install dependencies:

```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>

# Create a virtual environment (optional but recommended)
python -m venv venv
source venv/bin/activate   # (Linux/Mac)
venv\Scripts\activate    # (Windows)

# Install requirements
pip install -r requirements.txt
```

**Dependencies:**
- pandas, numpy, matplotlib  
- scikit-learn, statsmodels  
- xgboost (or fallback: RandomForestRegressor)  
- shap, lime  

## Usage
Open the notebook:

```bash
jupyter notebook airpassengers_lime_shap_paper_style_v2_annotated.ipynb
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

## Results (from Paper)
- ARIMA provides a strong seasonal baseline.  
- XGBoost/RandomForest with lagged features and seasonality encodings achieves lower RMSE and MAPE.  

**Interpretability Highlights:**
- `Lag_12` dominates due to yearly seasonality.  
- LIME shows local feature influence for specific months.  
- SHAP explains both global and local contributions, complementing LIME.  

## Citation
If you use this notebook in your research or teaching, please cite:

```
@misc{shukla2025airlime,
  title={Interpreting Time-Series Forecasts with LIME and SHAP: AirPassengers Case Study},
  author={Manish A. Shukla},
  year={2025},
  howpublished={GitHub Repository}
}
```

## Contributing
Pull requests are welcome! For major changes, please open an issue first to discuss what you’d like to add.

## Contact
- **Author**: Manish A. Shukla  
- **Email**: manishshukla.ms18@gmail.com  
- **LinkedIn**: [linkedin.com/in/manishshukla-ms](https://www.linkedin.com/in/manishshukla-ms)  
- **Website**: [manishshukla.com](https://www.manishshukla.com)  
