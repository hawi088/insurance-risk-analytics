# AlphaCare Insurance Solutions - Insurance Risk Analytics

## Project Overview

This project analyzes 18 months of historical insurance claim data (February 2014 – August 2015) for AlphaCare Insurance Solutions (ACIS), a South African auto-insurance company. The objective is to optimize marketing strategy, discover low-risk segments for premium reduction, and build predictive models for risk-based pricing.

## Business Impact

- Identify low-risk customer segments for targeted marketing
- Optimize premium pricing based on data-driven risk assessment
- Reduce loss ratio through better risk segmentation
- Enable evidence-based decision making for market expansion


---

## Task 1: Exploratory Data Analysis (EDA)

### Overview
Performed comprehensive EDA to understand data quality, distributions, and initial patterns in risk and profitability.

### Key Findings

**Loss Ratio Analysis:**
- Overall portfolio loss ratio: [Add your result]%
- Highest risk province: [Add province]
- Highest risk vehicle type: [Add vehicle type]
- Gender risk difference: [Add difference]%

**Data Quality:**
- Total records: 10,000 policies
- No missing values detected
- Clean data ready for analysis

**Temporal Trends:**
- Analyzed 18-month period (Feb 2014 - Aug 2015)
- Claim frequency and severity patterns identified

**Vehicle Risk:**
- Highest risk make: [Add make]
- Lowest risk make: [Add make]

### Visualizations Created
- Histograms for numerical feature distributions
- Bar charts for categorical variables
- Scatter plots (Premium vs Claims by ZipCode)
- Correlation matrix heatmap
- Geographic trend plots by province
- Box plots for outlier detection

### Key Metrics Created
- `LossRatio` = TotalClaims / TotalPremium
- `Margin` = TotalPremium - TotalClaims
- `HasClaim` = TotalClaims > 0

### Files Generated
- `notebooks/01_eda.ipynb` - Complete EDA notebook
- `src/eda_utils.py` - Reusable EDA functions

---

## Task 2: Data Version Control (DVC)

### Overview
Implemented DVC for reproducible, auditable data pipeline in compliance with insurance industry regulatory requirements.

### Data Versions

| Version | File | Description | Status |
|---------|------|-------------|--------|
| v1 | `data/insurance_data.csv` | Raw dataset (10,000 records) | Tracked |
| v2 | `data/insurance_data_cleaned.csv` | Cleaned dataset (duplicates removed, valid premiums) | Tracked |

### DVC Setup

**Remote Storage:** Local remote at `C:/dvc_storage`

**DVC Commands:**
```bash
# Initialize DVC
dvc init

# Add remote storage
dvc remote add -d localstorage C:/dvc_storage

# Track datasets
dvc add data/insurance_data.csv
dvc add data/insurance_data_cleaned.csv

# Push to remote
dvc push
```

### Reproducing the Data Pipeline
```bash
# 1. Clone the repository
git clone https://github.com/hawi088/insurance-risk-analytics.git
cd insurance-risk-analytics

# 2. Create virtual environment (optional but recommended)
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Install DVC
pip install dvc

# 5. Pull data from remote storage
dvc pull
```
### Verification Commands
```bash
# Check DVC status
dvc status

# List tracked files
dvc list . --dvc-only

# Verify remote configuration
dvc remote list
```

