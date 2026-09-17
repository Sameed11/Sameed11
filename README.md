<h1 align="center">Ahmed Sameed</h1>

<p align="center">
  Data Scientist · Dortmund, Germany<br/>
  MSc Data Science, University of Potsdam
</p>

<p align="center">
  <a href="https://linkedin.com/in/ahmed-sameed11"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/SQL-4479A1?style=flat&logo=mysql&logoColor=white">
  <img src="https://img.shields.io/badge/R-276DC3?style=flat&logo=r&logoColor=white">
  <img src="https://img.shields.io/badge/LightGBM-02569B?style=flat">
  <img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white">
  <img src="https://img.shields.io/badge/scikit--learn-F7931E?style=flat&logo=scikitlearn&logoColor=white">
  <img src="https://img.shields.io/badge/SQL_Server-CC2927?style=flat&logo=microsoftsqlserver&logoColor=white">
  <img src="https://img.shields.io/badge/Power_BI-F2C811?style=flat&logo=powerbi&logoColor=black">
  <img src="https://img.shields.io/badge/Flask-000000?style=flat&logo=flask&logoColor=white">
</p>

I work on time series and tabular problems end to end: SQL to get the data usable, scikit-learn
and PyTorch to model it, and enough engineering that the result reproduces. Each project below states
the baseline it beat, because an accuracy figure on its own tells you nothing.

Looking for my first full-time role — **Data Scientist, Data Analyst, Data Engineer or ML Engineer** —
in Germany or the EU.

<br/>

## Projects

### ⚡ [Day-ahead electricity demand forecasting](https://github.com/Sameed11/electricity-consumption-forecasting)
Turkish national grid load, 24 hours ahead. 39,456 hourly observations, rolling-origin backtest.

**2.79% MAPE · 55% better than seasonal naive**

Shipped LightGBM over a marginally better LSTM: the gap failed a paired *t*-test at 15x the
training cost. COVID broke the model, the write-up explains exactly why.

`LightGBM` `PyTorch` `time series` `backtesting` `pytest`

<br/>

### 🧠 [EEG attention state prediction](https://github.com/Sameed11/msc-thesis-eeg-attention) · MSc thesis
Attention states from 16-channel EEG across 9 subjects and 4 paradigms, validated leave-one-subject-out.

**97.4% accuracy · F1-macro 0.972**

States discovered by clustering rather than assigned in advance. Every prediction carries a
calibrated uncertainty estimate, so low-confidence outputs can be rejected instead of trusted.

`LightGBM` `XGBoost` `Transformer` `uncertainty quantification`

<br/>

### 💸 [Churn risk scoring](https://github.com/Sameed11/churn-risk-scoring)
7,043 telecom customers scored, then turned into a targeting decision with a price attached.

**AUC 0.858 · 3.1x top-decile lift · 2.8x campaign ROI**

Logistic regression chosen over boosting on purpose: 0.01 AUC is worth less than being able to
tell the retention team *why* a customer scored high. Flask service included.

`scikit-learn` `Flask` `decision analysis`

<br/>

### 🗄️ [SQL data warehouse](https://github.com/Sameed11/sql-data-warehouse-project)
ERP and CRM extracts integrated into a star schema. Bronze → silver → gold, T-SQL only.

**6 sources · 2 systems · no shared key format**

Stored-procedure loads per layer, so a data quality issue traces back to the layer that caused it.
Test scripts where zero rows returned means the check passed.

`T-SQL` `SQL Server` `medallion architecture` `data quality`

<br/>

### 🌿 [Plant disease CNN](https://github.com/Sameed11/plant-disease-cnn-classification)
Leaf disease classifier with augmentation, batch norm and dropout. **84.0% accuracy · F1 0.839**

`TensorFlow/Keras` `CNN`

### 🏠 [NRW rental price regression](https://github.com/Sameed11/rental-price-regression-nrw)
Price per m² from Immobilienscout24 listings. Exhaustive best-subsets under AIC *and* BIC, compared.

`R` `statistical inference`

<br/>

## Currently

Working through LLM application engineering — retrieval pipelines, evaluation, serving.
It gets pinned here when there's a result worth defending.
