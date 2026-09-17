# Ahmed Sameed

**Data Scientist** · Dortmund, Germany · MSc Data Science, University of Potsdam

I build forecasting and classification systems, and I care about whether the number
holds up. Most of what is below includes the baseline I had to beat, a significance
test, or the reason I picked the smaller model. The failures are in the READMEs too.

Open to Data Scientist, Data Analyst, Data Engineer and ML/AI Engineer roles across
Germany and the EU.

[LinkedIn](https://linkedin.com/in/ahmed-sameed11) · [Email](mailto:YOUR_EMAIL) · [CV](LINK_TO_PDF)

---

## Where to look, depending on what you're hiring for

| Role | Start here |
|---|---|
| Data Scientist | [Day-ahead load forecasting](https://github.com/Sameed11/electricity-consumption-forecasting) · [EEG attention states](https://github.com/Sameed11/msc-thesis-eeg-attention) |
| Data Analyst | [Churn risk scoring](https://github.com/Sameed11/churn-risk-scoring) · [NRW rental prices](https://github.com/Sameed11/rental-price-regression-nrw) |
| Data Engineer | [SQL data warehouse](https://github.com/Sameed11/sql-data-warehouse-project) · [forecasting pipeline](https://github.com/Sameed11/electricity-consumption-forecasting) |
| ML Engineer | [Backtest harness + leakage tests](https://github.com/Sameed11/electricity-consumption-forecasting) · [Flask scoring service](https://github.com/Sameed11/churn-risk-scoring) |

---

## Stack

**Languages** Python · SQL (T-SQL) · R
**ML** LightGBM · XGBoost · scikit-learn · PyTorch · TensorFlow/Keras · statsmodels
**Data** SQL Server · medallion ETL · pandas · Power BI
**Engineering** pytest · Flask · Git · CLI-reproducible experiments

---

## Projects

### [Day-ahead electricity demand forecasting](https://github.com/Sameed11/electricity-consumption-forecasting)
`Python` `LightGBM` `PyTorch` `time series` `backtesting`

24-hour-ahead forecasting of Turkish national grid load. 39,456 hourly observations
over 4.5 years, evaluated on a rolling-origin backtest of four 90-day folds with a
24-hour train/test gap.

- **2.79% MAPE, 55% better than the seasonal-naive baseline.**
- Shipped LightGBM over the marginally more accurate LSTM: the 1.8% gap failed a
  paired t-test (p = 0.34) and cost 15x the training time.
- An earlier version forecast one hour ahead against a persistence baseline. That
  baseline is illegal for day-ahead work, and the honest one is 1.9x harder to beat.
- COVID broke the model. Error rose 1.93x after March 2020 because 52% of it leaned
  on demand one and two weeks old. Weekly retraining recovered 23% of the gap, and
  the README says 23% rather than rounding it up.
- Prediction intervals hit 65.7% coverage against a 90% target. Documented as unfit
  for use, with conformalized quantile regression named as the fix.
- `pytest` leakage tests reconstruct every lag column independently.

### [EEG attention state prediction](https://github.com/Sameed11/msc-thesis-eeg-attention) — MSc thesis
`LightGBM` `XGBoost` `Transformer` `uncertainty quantification`

Two-stage meta-learning pipeline classifying attention states from 16-channel EEG,
across 9 subjects and 4 experimental paradigms, validated leave-one-subject-out.

- **97.4% accuracy, F1-macro 0.972** under LOSO cross-validation.
- States were discovered by k-means on spectral features rather than assigned in
  advance, which avoids the circularity of predicting labels you defined yourself.
- A LightGBM spectral specialist predicts 7 band-power targets (mean R² = 0.837),
  feeding three meta-learners: logistic regression, XGBoost, and a Transformer.
- Every model carries a calibrated uncertainty estimate. Wrong predictions run
  2–4x more uncertain than right ones (p < 10⁻⁶, Cohen's d > 1.7), so low-confidence
  outputs can be rejected instead of trusted.

### [Churn risk scoring with retention economics](https://github.com/Sameed11/churn-risk-scoring)
`scikit-learn` `Flask` `business analysis`

7,043 telecom customers scored for churn risk, then turned into a targeting decision:
who gets a retention offer, and what the campaign is worth.

- **Test AUC 0.858. Top-decile lift 3.1x**, catching 31% of all churners.
- Threshold economics costed out end to end: €49.4k net at a 0.3 cut-off, 2.8x ROI,
  against 1.3x for offering to everybody.
- Logistic regression chosen deliberately over gradient boosting. The ~0.01 AUC
  gain was not worth losing the sentence the retention team needs: *this customer
  scored high because of contract type and payment method.*
- Flask service in `deployment/` scores a single customer over HTTP; `train.py`
  reproduces the model from scratch.
- The README states plainly which findings are confounded and that the 30%
  offer-acceptance rate is invented until someone measures it.

### [SQL data warehouse: ERP + CRM sales analytics](https://github.com/Sameed11/sql-data-warehouse-project)
`T-SQL` `SQL Server` `medallion architecture` `data quality`

Six source files from two systems with no shared key format, landed and integrated
into a star schema. T-SQL only, no orchestration framework, so the ETL logic is
readable rather than hidden.

- Bronze / silver / gold schemas with stored-procedure loads per layer, so any data
  quality issue traces back to the layer that introduced it.
- Silver handles deduplication, date repair on 8-digit integer dates, sales
  reconciliation where `sales ≠ quantity × price`, and CRM-over-ERP source precedence.
- Test scripts written so that **zero rows returned means the check passed**:
  key uniqueness, referential integrity, range and consistency checks.
- Column-level `data_catalog.md` documenting grain and known limitations.

### [Plant disease CNN classification](https://github.com/Sameed11/plant-disease-cnn-classification)
`TensorFlow/Keras` `CNN` `image augmentation`

Leaf disease classifier built with Conv2D/BatchNorm/Dropout and augmentation.
**84.0% test accuracy, F1 0.839** on 1,862 held-out images.

### [NRW rental price regression](https://github.com/Sameed11/rental-price-regression-nrw)
`R` `statistical inference` `model selection`

Price per square metre across North Rhine-Westphalia from Immobilienscout24 listings.
Exhaustive best-subsets selection under both AIC and BIC via `bestglm`, with the two
criteria compared rather than one picked silently.

---

## Currently

Learning LLM application engineering: retrieval pipelines, evaluation, and serving.
Repo going up here once it does something worth reading about.
