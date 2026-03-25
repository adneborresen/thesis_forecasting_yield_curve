# Yield Curve Forecasting - Machine learning vs. Traditional Econometric Models

---
Note to self: Switch to daily data? Cross country comparison still possible, but macro-data problematic.


### Data
We use data from the US and Norway, with a time period of 2003-2024. [Explanation of datasets]

### Methodology
We use a Dynamic Nelson-Siegel model to forecast the yield curve for the US and Norway. We compare the performance of a Vector Autoregression (VAR) model with a Long Short-Term Memory (LSTM) model, considering whether either model performs better on Norwegian or US data. We also include a Random Walk model as a benchmark. We then include macroeconomic factors to see if they improve the performance of the models, and whether this macro-augmentation differs between the two countries.

#### Forecasting horizon
We forecast the yield curve for 1, 3, 6 and 12 months ahead using expanding window. We begin the out of sample period from January 2015. 
Roughly, this gives 144 months in-sample (12 years) and 120 months out-of-sample (10 years), and allows our OOS period to include the COVID-19 pandemic and the subsequent period of high inflation. [Look at the literature!!]


#### Evaluation
We use Diebold-Mariano test to compare the performance of the models, together with RMSE and MAE.


#### Macro-variables:
Follow what  Diebold-Rudebusch-Aruoba (2006) did?
Real Activity: Specifically, the year-over-year (YoY) growth in industrial production.
Inflation: Specifically, the year-over-year (YoY) Consumer Price Index (CPI).
Monetary Policy Instrument: Specifically, the Federal Funds Rate

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
