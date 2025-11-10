# A Logistic Approach to Heart Disease Diagnosis

## Final Report (PDF)

**[Stat_330_Final_Project_Jenna_and_Ellee.pdf](Stat_330_Final_Project_Jenna_and_Ellee.pdf)**  
*Click to view the complete 14-page report — abstract, introduction, EDA, models, predictions, conclusions, and appendix.*

> This PDF is the **final, official report** by Jenna Worthen and Ellee Millard (dated December 11, 2024). It details the full analysis, figures, tables, and findings.

## Project Summary

This project analyzes the **UCI Heart Disease Dataset** (merged from hospitals in Ohio, Hungary, Switzerland, and California; 920 patients with 16 variables including age, sex, cholesterol, blood pressure, and heart disease stage from 0-4). The data focuses on clinical measurements to predict heart disease risk. We binarized the outcome into reversible (stages 0-1) vs. irreversible (stages 2-4) and applied **logistic regression** in two models:  
- **Simple Model**: Uses easily obtainable predictors (age, sex, maximum heart rate during exercise, resting systolic blood pressure) for quick assessment without medical tests.  
- **Medical Model**: Incorporates advanced predictors (exercise-induced chest pain, left ventricular hypertrophy, cholesterol, thalassemia defects, ST segment recovery impairment) requiring hospital testing.  

Variable selection via AIC identified key factors like recovery impairment and sex. Models were fitted using `glm()` in R (binomial family), with odds ratios for interpretability (e.g., being male increases odds by 3.21 in the simple model). Assumptions (linearity in log-odds, no multicollinearity via VIF <5, no influential outliers) were verified. Predictive performance was evaluated via 80/20 train-test split, confusion matrices, ROC curves (AUC: 0.749 simple, 0.814 medical), and cutoff optimization (0.625 simple, 0.45 medical) to balance sensitivity/specificity/accuracy (~73-77%). The medical model slightly outperforms, but both highlight actionable risk factors for prevention.

## Interactive Report (Rendered Quarto)

The full analysis is written in **Quarto** — a reproducible format with embedded R code, outputs, and narrative.  
GitHub renders `.qmd` files inline as formatted reports (no raw code visible by default).

### [View Rendered Report → `HEART_PROJ_CODE.qmd`](HEART_PROJ_CODE.qmd)

> Includes libraries, data loading/cleaning, EDA plots (violin, jitter, correlation), variable selection, model summaries, assumptions checks, predictions, ROC, and cutoff optimization.

## Data

| File | Description |
|------|-------------|
| [`heart.csv`](heart.csv) | UCI Heart Disease dataset (920 rows; cleaned with renamed columns like `max_hr`, `resting_bp`) |

## Reproduce the Analysis

```bash
# 1. Clone the repo
git clone https://github.com/cottonjenn/Logistic-Approach-to-Heart-Disease.git
cd Logistic-Approach-to-Heart-Disease

# 2. Install Quarto (if needed)
#    → https://quarto.org/docs/get-started/

# 3. Install R packages (run in R console)
install.packages(c("ggplot2", "dplyr", "MASS", "reshape2", "car", "GGally", "patchwork", "pROC", "caret", "gridExtra", "corrplot", "bestglm"))

# 4. Render the report
quarto render heart_disease_report.qmd  # Regenerates PDF with all outputs
