# End-to-End Insurance Risk Analytics & Predictive Modeling

This project analyzes historical car insurance claim data for AlphaCare Insurance Solutions (ACIS). 
The goal is to identify low-risk customer segments and build predictive models for premium optimization.

## Project Structure
- data/ → raw and processed datasets
- notebooks/ → Jupyter notebooks for EDA and modeling
- src/ → Python modules for data processing, modeling pipelines
- scripts/ → standalone scripts
- visuals/ → plots and images used in reports
- reports/ → interim and final reports

## Tasks Completed
- Task 1: Git setup + Exploratory Data Analysis (ongoing)
- Task 2: DVC setup (pending)

# AlphaCare Insurance Risk Analytics - Task 1

## Project Overview
This repository contains the work for **Task 1** of the End-to-End Insurance Risk Analytics & Predictive Modeling challenge at **AlphaCare Insurance Solutions (ACIS)**.  
The objective of Task 1 is to perform **Exploratory Data Analysis (EDA) and basic statistical analysis** on historical car insurance data to uncover patterns in risk, profitability, and claims.

---

## Task 1 Structure

### 1.1 Git & GitHub Setup
- Git repository created with proper version control
- Branching strategy used:
  - `main` – main branch
  - `task-1` – development branch for Task 1 work
- Commits are descriptive and frequent to track daily progress
- GitHub Actions configured for basic CI (if applicable)

### 1.2 Exploratory Data Analysis (EDA) & Statistics
- **Objective:** Understand the dataset, assess data quality, and extract insights to guide insurance risk analysis.
- **Dataset Used:** `MachineLearningRating_v3.txt` (pipe-delimited)
- **Key Analyses Performed:**
  - Data quality assessment (missing values, data types)
  - Descriptive statistics (numerical and categorical)
  - Loss Ratio calculation (`TotalClaims / TotalPremium`)
  - Outlier detection (`TotalClaims`, `CustomValueEstimate`)
  - Temporal trends over 18 months
  - Geographic analysis (Province & PostalCode)
  - Vehicle Make/Model analysis
  - Gender-based analysis
  - Creative visualizations (heatmaps, scatter plots, temporal trends)

---

## File Structure
- data/
    - MachineLearningRating_v3.txt # Raw dataset
- notebooks/
    - eda.ipynb # Task 1 EDA notebook
- README.md # Project description and instructions


---

## Usage Instructions

1. **Clone the repository:**

```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
```
2. **Create a virtual environment (optional but recommended):**
```bash 
python -m venv venv
source venv/bin/activate  # Linux/Mac
venv\Scripts\activate     # Windows
```
3. **Install required packages:**
```bash
pip install pandas matplotlib seaborn numpy
```
4. **Run the EDA notebook:**
```bash
jupyter notebook notebooks/eda.ipynb
```
The notebook contains step-by-step analysis, visualizations, and insights.

## Task 2 — Data Version Control (DVC)
### Objective

Establish a reproducible and auditable data pipeline using DVC, ensuring that datasets and analyses can be tracked and reproduced for compliance and debugging.

**Steps Completed**

**1. DVC Initialization**
```bash
pip install dvc
dvc init
```
**2. Local Remote Storage**
```bash 
mkdir D:\tenx\dvc-storage
dvc remote add -d localstorage D:\tenx\dvc-storage 
```
**3. Dataset Tracking**
```bash
dvc add data/MachineLearningRating_v3.txt
git add data/.gitignore data/MachineLearningRating_v3.txt.dvc
git commit -m "Track dataset with DVC for Task 2"
```
**3. Push Data to Remote**
```bash
dvc push
```
### Outcome
- Dataset is versioned and reproducible
- DVC pipeline ensures auditability and compliance
- Task 2 branch is ready to merge into main
## Task 3: Statistical Hypothesis Testing
### Objective
The goal of Task 3 was to statistically validate or reject key hypotheses about insurance risk drivers. This analysis informs our segmentation strategy, helping AlphaCare Insurance Solutions optimize premiums and identify low-risk target segments.

### Key Performance Indicators (KPIs)
- Claim Frequency: Proportion of policies with at least one claim.
- Claim Severity: Average claim amount, given a claim occurred.
- Margin: TotalPremium – TotalClaims, representing profitability.
### Hypotheses Tested
1. H₀: There are no risk differences across provinces.
2. H₀: There are no risk differences between zip codes.
3. H₀: There is no significant margin (profit) difference between zip codes.
4. H₀: There is no significant risk difference between women and men.
### Methodology
- **Data Segmentation:** The dataset was grouped based on the feature under test (Province, Gender, PostalCode).
- **Statistical Tests:** 
    - Chi-Square Test: Used for categorical features (Province, Gender, PostalCode) to test association with claim occurrence.
    - ANOVA Test: Used for numerical features (VehicleAge, CustomValueEstimate, Margin) to test differences in means.
- Significance Level: 0.05 (95% confidence level).
- Interpretation: If p-value < 0.05 → reject null hypothesis (feature significantly affects KPI).
### Results
| Feature             | Test       | Statistic | p-value   | Significant |
| ------------------- | ---------- | --------- | --------- | ----------- |
| Province            | Chi-Square | 104.19    | 5.93e-19  | Yes         |
| Gender              | Chi-Square | 7.26      | 0.0265    | Yes         |
| VehicleAge          | ANOVA      | 10.58     | 2.64e-05  | Yes         |
| CustomValueEstimate | ANOVA      | 7.97      | 0.00038   | Yes         |
| Margin              | ANOVA      | 668.55    | 1.86e-290 | Yes         |

**Interpretation:**
- All tested features are statistically significant, meaning they have a measurable effect on claim frequency, severity, or margin.
- **Business Implication:**
  - Premiums may be adjusted by province and gender.
  - High-value vehicles and older vehicles should be evaluated for adjusted premiums.
  - Policies with higher margins indicate profitable segments for targeted marketing.
  ## Usage
1. Load the dataset (MachineLearningRating_v3.txt) with | as the separator.
2. Run task3_analysis.ipynb to reproduce the hypothesis tests and tables.
3. The outputs include Chi-Square and ANOVA results with p-values and business interpretation.