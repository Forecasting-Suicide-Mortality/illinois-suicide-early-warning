# Detecting Silent Early Signals of Mental Health Crises

### A Time-Series Early Warning System for Illinois Suicide Prevention

**Team:** Hoon Yum, Adaora Ezike, Eduardo Tovilla Rivera, Payton Stewart  
**Program:** MS in Applied Data Science | University of Chicago  
**Course:** ADSP 31006 — Time Series Analysis and Forecasting

---

## Background & Motivation

Illinois has experienced a **53.6% increase** in suicide deaths over the past 25 years (1999–2023), rising from 85.0 to 130.6 deaths per month. Despite the launch of the 988 Suicide & Crisis Lifeline in July 2022, suicide rates have continued to climb, reaching historic peaks of **1,567 annual deaths** in 2022–2023.

This project develops a **Bayesian Structural Time Series (BSTS)** early warning system to predict suicide surges **2–6 weeks in advance**, enabling proactive resource allocation and preventive interventions.

---

## Data Sources

| Source                                                       | Description                                                  | Period    |
| ------------------------------------------------------------ | ------------------------------------------------------------ | --------- |
| [CDC WONDER — Multiple Cause of Death](https://wonder.cdc.gov/mcd-icd10.html) | Finalized monthly suicide mortality (ICD-10: X60–X84, Y87.0) | 1999–2020 |
| [CDC WONDER — Provisional Mortality](https://wonder.cdc.gov/mcd-icd10-provisional.html) | Provisional monthly suicide mortality                        | 2021–2023 |
| Google Trends                                                | Mental health search volume ("suicide", "crisis", "depression", "988") | 2004–2023 |
| Bureau of Labor Statistics                                   | Illinois monthly unemployment rate                           | 1999–2023 |
| NOAA                                                         | Extreme weather events                                       | 1999–2023 |

**Total observations:** N = 300 months (25 years)

---

## Key Findings

- **Strong upward trend:** R² = 0.54 (p < 0.001), significant 25-year linear increase of +1.96 deaths/year
- **Seasonal pattern:** 23.4% amplitude — summer peak (Aug: 114.3/month) vs. winter low (Feb: 92.6/month)
- **COVID paradox:** Suicides decreased 3.8% during the pandemic (2020–21) but rebounded +5.9% post-COVID to historic highs
- **Post-988 trajectory:** Deaths increased 7.2% after 988 launch (Jul 2022), continuing the long-term trend

---

## Methodology

### Model: Bayesian Structural Time Series (BSTS)

The BSTS model decomposes the suicide mortality series into interpretable components:

- **Trend:** Captures long-term increase (+1.96 deaths/year)
- **Seasonality:** Models 12-month cycle (23.4% amplitude)
- **Regression:** Incorporates lead indicators (Google Trends, unemployment, weather)
- **Interventions:** COVID-19 onset (Mar 2020), 988 Lifeline launch (Jul 2022)

### Validation Strategy

- **Training set:** 1999–2021
- **Test set:** 2022–2023
- **Target:** 80%+ forecast accuracy for 2–6 week ahead predictions

---

## Project Structure

```
├── data/
│   ├── raw/                  # Raw CDC WONDER exports
│   ├── processed/            # Cleaned and merged datasets
│   └── external/             # Google Trends, BLS, NOAA data
├── src/
│   ├── data_collection.R     # Data acquisition and merging
│   ├── eda.R                 # Exploratory data analysis
│   ├── feature_engineering.R # Lead indicator processing
│   ├── bsts_model.R          # BSTS model development
│   └── evaluation.R          # Model validation and diagnostics
├── outputs/
│   ├── figures/              # Visualizations and plots
│   └── dashboard/            # Early warning dashboard
├── docs/
│   ├── proposal.pdf          # Project proposal
│   └── final_report.pdf      # Final report
└── README.md
```

---

## Tech Stack

- **Language:** R
- **Core Package:** `bsts` (Bayesian Structural Time Series)
- **Supporting:** `tidyverse`, `forecast`, `zoo`, `xts`, `ggplot2`
- **Data APIs:** `gtrendsR`, `blsAPI`

---

## Expected Outcomes

1. **Predictive Model:** Forecast suicide surges 2–6 weeks in advance with 80%+ accuracy
2. **Early Warning Dashboard:** Real-time visualization of predicted high-risk periods
3. **Policy Recommendations:** Evidence-based guidance for 988 staffing, crisis bed capacity, and outreach timing
4. **Public Health Impact:** Enable proactive interventions during predicted surge periods

---

## Team

| Member                     | Role |
| -------------------------- | ---- |
| **Junghoon(Hoon) Yum**     | TBD  |
| **Adaora Ezike**           | TBD  |
| **Eduardo Tovilla Rivera** | TBD  |
| **Payton Stewart**         | TBD  |

---

## References

- CDC WONDER: [https://wonder.cdc.gov](https://wonder.cdc.gov)
- Scott, S.L. & Varian, H.R. (2014). *Predicting the Present with Bayesian Structural Time Series.* International Journal of Mathematical Modelling and Numerical Optimisation.
- 988 Suicide & Crisis Lifeline: [https://988lifeline.org](https://988lifeline.org)

---

## License

This project is for academic purposes as part of the University of Chicago MS in Applied Data Science program.
