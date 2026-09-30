# 📊 Finance Performance & Budget Analysis
### A Data Analyst Portfolio Project — 12-Month P&L, Budget Variance & Management Insights

---

## 🎯 Project Overview

This project analyses a synthetic 12-month P&L dataset for a business operating across April–March (Indian financial year). It was built to demonstrate core **data analyst skills** applied to a real-world finance domain problem.

| | |
|---|---|
| **Role Target** | Data Analyst / Finance Analyst |
| **Domain** | Financial reporting, budget variance, profitability analysis |
| **Dataset** | Synthetic / illustrative — 12 months, ₹ Lakhs |
| **Tools** | Python · pandas · matplotlib · seaborn · openpyxl · Jupyter |
| **Output** | Jupyter Notebook · Excel report · Charts (PNG) |

---

## 📁 Project Structure

```
PnL_analysis/
│
├── data/
│   └── pnl_data.xlsx           ← Source data (Excel, 7 sheets)
│
├── notebooks/
│   └── PnL_Analysis.ipynb      ← Main analysis notebook (13 sections)
│
├── outputs/
│   ├── charts/                 ← All exported visualisations (PNG)
│   │   ├── kpi_cards.png
│   │   ├── revenue_trend.png
│   │   ├── margin_trends.png
│   │   ├── budget_vs_actual.png
│   │   ├── opex_analysis.png
│   │   ├── tax_sensitivity.png
│   │   └── correlation_heatmap.png
│   └── reports/
│       └── PnL_Summary_Report.xlsx  ← Python-generated summary workbook
│
├── PnL_Analysis_Model.xlsx     ← Master financial model (corrected Book 2)
├── run_analysis.py             ← Script to automate chart & report generation
└── README.md                   ← Project documentation & interview guide
```

---

## 🔧 How to Run

### 1. Clone / open the project
`ash
cd PnL_analysis
`

### 2. Install dependencies
`ash
pip install pandas openpyxl matplotlib seaborn scipy jupyter
`

### 3. Launch the notebook
`ash
jupyter notebook notebooks/PnL_Analysis.ipynb
`

> Run all cells top-to-bottom (Cell → Run All).  
> Charts are saved automatically to outputs/charts/.  
> The Excel summary report is saved to outputs/reports/.

---

## 📊 What the Notebook Covers

| Section | Topic |
|---|---|
| 1 | Setup & library imports |
| 2 | Data load & validation (null checks, type checks) |
| 3 | Feature engineering — full P&L built in pandas with single-cell **tax rate assumption** |
| 4 | Full-year KPI dashboard (Revenue, Gross Margin, EBITDA, Net Profit) |
| 5 | Monthly revenue trend & MoM growth analysis |
| 6 | Margin trends — Gross / EBITDA / Net Profit / OpEx % |
| 7 | Budget vs Actual variance — colour-coded FAV / UNFAV |
| 8 | Operating expense deep-dive & stacked composition chart |
| 9 | Tax modelling & sensitivity analysis |
| 10 | Management insights & KPI summary |
| 11 | Correlation heatmap |
| 12 | Export to Excel summary report |
| 13 | Conclusions & recommendations |

---

## 🔑 Key Findings & Interview Insights

### 1 · Revenue beat, OpEx overrun — EBITDA missed

| Metric | Budget | Actual | Variance | Signal |
|---|---|---|---|---|
| Revenue | ₹1,150L | ₹1,189L | +₹39L (+3.4%) | ✅ FAV |
| Operating Expenses | ₹275L | ₹301.5L | +₹26.5L (+**9.6%**) | ❌ UNFAV |
| EBITDA | ₹245L | ₹238.5L | -₹6.5L (-2.6%) | ❌ UNFAV |
| Net Profit | ₹145L | ₹170.1L | +₹25.1L (+**17.3%**) | ✅ FAV* |

> *Net profit beat is a **below-EBITDA cost windfall**, not operational outperformance.

### 2 · The below-EBITDA explanation

Budget implied **₹100L** in below-EBITDA costs (Depreciation + Interest + Tax).  
Actual costs were only **₹68.4L** — a **₹31.6L saving** that converted the EBITDA miss into a Net Profit beat.  
An interviewer will ask this question. The answer is in Section 10.

### 3 · Revenue growth: choose your metric carefully

| Metric | Value | Notes |
|---|---|---|
| Endpoint growth (Apr → Mar) | **43.9%** | Misleading — compares only two months |
| Compound MoM growth | **~3.4%** | More defensible — geometric average over 11 intervals |
| Arithmetic MoM average | **~3.5%** | Consistent with compound figure |

### 4 · Tax rate consistency

The original data had hardcoded monthly tax values causing the effective rate to drift from **23%** (April) to **15%** (March) with no business justification.  
This project uses a **single TAX_RATE = 20% input cell** — change once, recalculate everything.

---

## 🛠 Skills Demonstrated

| Skill | Where |
|---|---|
| **Excel / openpyxl** | Reading multi-sheet workbook, parsing formulas |
| **pandas** | Data cleaning, P&L calculation pipeline, grouping |
| **matplotlib / seaborn** | Bar, line, stacked bar, heatmap, KPI cards |
| **Financial modelling** | P&L structure, margin analysis, variance analysis |
| **Business storytelling** | Translating numbers into management insights |
| **Assumption management** | Single tax-rate input, sensitivity tables |
| **Python scripting** | Automated chart export, Excel report generation |

---

## 📌 Notes

- All data is **synthetic and illustrative** — created for portfolio and learning purposes only.
- Amounts are in **₹ Lakhs** (1 Lakh = 100,000 INR).
- The financial year runs **April to March** (Indian FY convention).
- `PnL_Analysis_Model.xlsx` (and `data/pnl_data.xlsx`) contains 7 worksheets ordered by analytical workflow:
  1. Project Overview
  2. Raw Data
  3. P&L Analysis
  4. Budget Variance
  5. Monthly Analysis
  6. Management Insights
  7. Dashboard
