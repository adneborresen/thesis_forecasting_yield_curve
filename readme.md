# Yield Curve Forecasting - Machine learning vs. Traditional Econometric Models

---

## Repository Structure

```
thesis_forecasting_yield_curve/
├── CONFIG.py                          # Global configuration (paths, parameters)
├── LICENSE
├── readme.md
├── .gitignore
│
├── data/
│   ├── raw/                           # Original, unprocessed datasets
│   │   ├── us/
│   │   └── norway/
│   └── processed/                     # Cleaned & transformed data
│       ├── us/
│       └── norway/
│
├── notebooks/
│   ├── 00_build_data.ipynb            # Data ingestion, preprocessing & raw data exploration
│   ├── 01_data_visualization.ipynb    # Processed data visualisation & summary
│   ├── 02_random_walk.ipynb           # Random walk benchmark model
│   ├── 03_var_dns.ipynb               # VAR Dynamic Nelson-Siegel model
│   ├── 04_var_macro_dns.ipynb         # VAR DNS with macroeconomic factors
│   ├── 05_lstm_dns.ipynb              # LSTM Dynamic Nelson-Siegel model
│   ├── 06_lstm_macro_dns.ipynb        # LSTM DNS with macroeconomic factors
│   └── 07_results.ipynb              # Model comparison & evaluation
│
│
└── outputs/
    ├── figures/                       # Generated plots & visualisations
    │   ├── us/
    │   └── norway/
    ├── models/                        # Saved / serialised model artefacts
    │   ├── us/
    │   └── norway/
    ├── predictions/                   # Model forecast outputs
    │   ├── us/
    │   └── norway/
    └── tables/                        # Result tables (LaTeX / CSV)
        ├── us/
        └── norway/
```
