# Logistic Approach to Heart Disease – Final Report

![Python](https://img.shields.io/badge/Python-3.9+-blue?logo=python)
![Quarto](https://img.shields.io/badge/Quarto-1.4+-purple?logo=quarto)
![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)

## Final Report (PDF)

**[Heart_Disease_Logistic_Report.pdf](Heart_Disease_Logistic_Report.pdf)** – *All findings, methodology, model results, and visualisations.*

> This PDF is the **complete, self-contained report** of the project.  
> Click to view inline on GitHub or download for offline reading.

---

## Data

| File | Description |
|------|-------------|
| `heart.csv` | Raw UCI Heart Disease dataset used for modeling |

---

## Reproducing the Analysis

The PDF was generated from a **Quarto (`.qmd`)** source file that contains every step:

```bash
# 1. Clone
git clone https://github.com/cottonjenn/Logistic-Approach-to-Heart-Disease.git
cd Logistic-Approach-to-Heart-Disease

# 2. Install dependencies
pip install -r requirements.txt   # pandas, scikit-learn, matplotlib, seaborn, etc.

# 3. Render the report (optional – re-creates the PDF)
quarto render heart_disease_report.qmd
