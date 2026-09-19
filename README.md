# Monthly Global Solar Radiation Prediction: Empirical Models, Metaheuristics and TFT Benchmark

## 1. Project Overview
This repository contains the dataset, optimization algorithms, and benchmark scripts associated with the manuscript:
**"A hybrid empirical model for monthly global solar radiation prediction under limited data conditions: optimization, stability analysis and comparison with the Temporal Fusion Transformer"**

The project evaluates eight Angström-Prescott-type empirical formulations calibrated via Ordinary Least Squares (OLS), Particle Swarm Optimization (PSO), and the Pelican Optimization Algorithm (POA), alongside a Temporal Fusion Transformer (TFT) deep-learning benchmark under data-scarce conditions (75 months).

---

## 2. Dataset Information
- **Data File:** `01_monthly_data.csv`
- **Location:** Çiğli Airport meteorological station (WMO: 17218, ICAO: LTBL), İzmir, Türkiye (38°30' N, 27°01' E, 5 m a.s.l.).
- **Period:** January 2018 – March 2024 (75 monthly records).
- **Partition:** 63 months training (2018-01 to 2023-03), 12 months test (2023-04 to 2024-03).
- **Columns:**
  - `Year`, `Month`: Date index
  - `H`: Monthly average daily global solar radiation (Wh/m²/day)
  - `H0`: Extraterrestrial radiation (Wh/m²/day)
  - `S_S0`: Sunshine duration ratio (S/S₀)
  - `H_H0`: Clearness index ratio (H/H₀)

*Note: Raw daily observations were obtained from the Turkish State Meteorological Service (MGM) under restricted access. Derived monthly aggregates are provided here for full scientific reproducibility.*

---

## 3. Environment & Requirements
The code is designed to run in standard Python 3.9+ environments or directly on **Google Colab**.

Key dependencies:
- `numpy`
- `pandas`
- `scipy`
- `scikit-learn`
- `matplotlib`
- `seaborn`
- `torch`
- `darts`

---

## 4. Usage Instructions

### Running on Google Colab:
1. Open the provided Jupyter/Colab notebook (`.ipynb`) in Google Colab.
2. Upload `01_monthly_data.csv` to your Google Drive or Colab runtime root.
3. Execute the cells sequentially to run model fitting, walk-forward cross-validation, and stability tests.
4. Generated output tables, metrics, and figure files will be automatically exported to `/content/review_evidence_pack`.

### Running Locally:
Clone the repository and install requirements:
```bash
git clone [https://github.com/serkanansay/solar-forecasting-analysis.git](https://github.com/serkanansay/solar-forecasting-analysis.git)
cd solar-forecasting-analysis
pip install numpy pandas scipy scikit-learn matplotlib seaborn torch darts
python run_analysis.py
