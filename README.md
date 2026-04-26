# Lending Club Credit Risk Analysis

## Overview
Rule-based credit risk scoring system built on 1.3M real loan records (2007–2018). 
Identifies high-risk borrowers without ML — using business logic validated with 
statistical testing.

**Live Dashboard:** [Looker Studio](https://datastudio.google.com/reporting/4145e81e-29c9-46d2-9bd0-30c0cf7c6268)

---

## Business Questions Answered
1. What borrower attributes are most predictive of default?
2. Can we build a rule-based risk tier system without ML?
3. What is the financial impact of flagging the riskiest 22% of borrowers?
4. Are these risk factors statistically significant?

---

## Key Findings
| Metric | Value |
|--------|-------|
| Dataset size | 1,345,310 loans |
| Overall default rate | 20.0% |
| Grade A default rate | 6.0% |
| Grade G default rate | 49.9% |
| Very High risk tier default rate | 46.2% |
| Defaults prevented (policy simulation) | 105,497 (39.3% of all defaults) |
| Losses prevented | $1.52B |

---

## Risk Scoring System
Built a 0–100 point rule-based risk score using 5 key attributes:
- **Loan grade** (0–40 pts) — strongest predictor
- **Debt-to-Income ratio** (0–20 pts)
- **Interest rate** (0–20 pts)
- **Delinquencies in last 2 years** (0–10 pts)
- **Public record bankruptcies** (0–10 pts)

### Risk Tiers
| Tier | Loans | Default Rate |
|------|-------|-------------|
| Low (0–20) | 473,611 | 9.1% |
| Medium (21–40) | 574,711 | 20.9% |
| High (41–60) | 243,376 | 33.2% |
| Very High (61–100) | 53,612 | 46.2% |

---

## Statistical Validation
- Interest rate difference (defaulted vs paid): **15.71% vs 12.62%**, p < 0.001
- DTI difference: **20.17 vs 17.81**, p < 0.001
- Risk score correlation with default: **r = 0.265**, p < 0.001

---

## Tools & Stack
- **Python** — pandas, numpy, scipy (statistical testing)
- **Kaggle Notebooks** — cloud compute for 1.3M row dataset
- **Looker Studio** — interactive dashboard
- **Excel** — executive summary and pivot tables

---

## Files
| File | Description |
|------|-------------|
| `notebook.ipynb` | Full analysis notebook |
| `lending_club_risk_analysis.xlsx` | Excel summary (4 sheets) |
| `looker_data.xlsx` | Aggregated data for dashboard |

---

## How to Run
1. Open notebook on Kaggle (dataset auto-attached)
2. Run all cells (~10 minutes for full dataset)
3. Download output files from `/kaggle/working`
