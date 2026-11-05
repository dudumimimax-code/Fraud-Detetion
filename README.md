# Fraud Detection: Card Transaction Monitor

A machine learning solution that classifies card transactions as fraudulent or legitimate, plus an interactive dashboard to monitor the results.

**Live dashboard:** https://dudumimimax-code.github.io/Fraud-Detetion/

## Highlights

- **Random Forest (200 trees)** trained on 523k labelled transactions from 2025 and validated out-of-time: trained on January–November, tested on December, a month the model never saw.
- **Feature selection:** hour of day, new device, transaction value, merchant, city and device type carry the signal. Internal score, temperature, weekday, postal code and customer history showed none and were removed.
- **Imbalanced data:** only 3.9% of transactions are fraud, so the evaluation uses precision, recall and PR-AUC instead of accuracy.
- **Interactive dashboard** with a city × hour risk map, diagnostics by hour, merchant, device and value, and AI-driven insights that update in real time with the filters.

## Results (December hold-out)

| Metric | Value |
|---|---|
| Recall | 70% of frauds caught |
| Precision | 53% of flags are fraud |
| PR-AUC | 0.61 (random guess ≈ 0.05) |

## Structure

```
dashboard/index.html   Self-contained dashboard (data embedded)
notebook/              Analysis and model training notebook (outputs included)
```

## Data

The transaction files come from a case study and are not published here. The notebook expects `transacoes_historico_2025.csv` and the January 2026 file in the same folder (or in `ATF-DataScience/`).

## Tech

Python, pandas, scikit-learn, matplotlib · Chart.js dashboard
