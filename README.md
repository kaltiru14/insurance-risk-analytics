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