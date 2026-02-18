# Detecting Silent Early Signals of Mental Health Crises

### A Time-Series Early Warning System for Illinois Suicide Prevention

**Team:** Junghoon(Hoon) Yum, Adaora Ezike, Eduardo Tovilla Rivera, Payton Stewart  
**Program:** MS in Applied Data Science | University of Chicago  
**Course:** ADSP 31006 — Time Series Analysis and Forecasting

---

## Background & Motivation

Illinois has experienced a **53.6% increase** in suicide deaths over the past 25 years (1999–2023), rising from 85.0 to 130.6 deaths per month. Despite the launch of the 988 Suicide & Crisis Lifeline in July 2022, suicide rates have continued to climb, reaching historic peaks of **1,567 annual deaths** in 2022–2023.

This project develops a **Time Series Model** early warning system to predict suicide surges **2–6 weeks in advance**, enabling proactive resource allocation and preventive interventions.

---

## Data Sources

| Source                                                       | Description                                                  | Period    |
| ------------------------------------------------------------ | ------------------------------------------------------------ | --------- |
| [CDC WONDER — Multiple Cause of Death](https://wonder.cdc.gov/mcd-icd10.html) | Finalized monthly suicide mortality (ICD-10: X60–X84, Y87.0) | 1999–2020 |
| [CDC WONDER — Provisional Mortality](https://wonder.cdc.gov/mcd-icd10-provisional.html) | Provisional monthly suicide mortality                        | 2021–2023 |

**Total observations:** N = 300 months (25 years)

---

## Key Findings


---

## Methodology

### Model: 



### Validation Strategy


---

## Project Structure

```
├── data/
│   ├── raw/                  # Raw CDC WONDER exports
│   ├── processed/            # Cleaned and merged datasets
│   └── external/             # External data
├── src/
│   ├── data_collection.R     # Data acquisition and merging
│   ├── eda.R                 # Exploratory data analysis
│   ├── feature_engineering.R # Lead indicator processing
│   ├── ts_model.R            # Model development
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
- **Supporting:** `tidyverse`, `forecast`, `zoo`, `xts`, `ggplot2`

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
- 988 Suicide & Crisis Lifeline: [https://988lifeline.org](https://988lifeline.org)

---

## License

This project is for academic purposes as part of the University of Chicago MS in Applied Data Science program.
