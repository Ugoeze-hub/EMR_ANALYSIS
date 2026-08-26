# Electronic Medical Record (EMR) Adoption & Performance Analysis

A data-driven evaluation of Electronic Medical Record (EMR) system implementation across healthcare facilities. This project cleans, standardizes, and analyzes survey responses collected online and offline from healthcare professionals (doctors, nurses, administrative staff, IT support, and lab personnel).

The evaluation assesses demographic distributions, technical EMR complexity, infrastructure barriers (network outages, power supply), technical support turnaround times, training coverage, and organizational leadership support.

---

## Repository Structure

```
EMR_ANALYSIS/
├── README.md                           <- Top-level project overview & guide
├── requirements.txt                    <- Python package dependencies
├── .gitignore                          <- Git rules for data, checkpoints & environment files
├── data/                               <- Data directory layout
│   ├── raw/                            <- Immutable raw survey datasets (.xlsx)
│   ├── processed/                      <- Cleaned & merged analysis datasets (.xlsx)
│   └── README.md                       <- Data governance & schema guide
├── notebooks/                          <- Sequential Jupyter notebooks
│   ├── 01_preprocessing.ipynb          <- Data cleaning, column standardization & merging
│   ├── 02_exploratory_analysis.ipynb   <- Initial EDA & univariate distributions
│   └── 03_final_analysis.ipynb         <- Advanced statistical evaluation & visualization export
├── reports/                            <- Analytical summaries & generated figures
│   ├── figures/                        <- Categorized visualization plots (.png)
│   │   ├── demographics/               <- Age, gender, education & profession distributions
│   │   ├── technical_complexity/       <- EMR rating & perceived complexity charts
│   │   └── infrastructure_support/     <- Network, power, leadership & support charts
│   └── README.md                       <- Visualization catalog & insights summary
└── src/                                <- Extensible Python package code
    └── __init__.py
```

---

## Pipeline & Execution Order

To reproduce the analysis from scratch:

1. **Place Raw Datasets**:
   - Save online survey data as `EMR analysis online.xlsx` inside [`data/raw/`](data/raw/).
   - Save offline audit data as `EMR analysis offline.xlsx` inside [`data/raw/`](data/raw/).

2. **Run Ingestion & Preprocessing**:
   - Open and execute [`notebooks/01_preprocessing.ipynb`](notebooks/01_preprocessing.ipynb).
   - This cleans organizational factors, standardizes column schemas across online/offline instruments, and exports merged datasets to [`data/processed/`](data/processed/).

3. **Run Exploratory Analysis**:
   - Execute [`notebooks/02_exploratory_analysis.ipynb`](notebooks/02_exploratory_analysis.ipynb) to inspect key category groupings.

4. **Run Statistical Analysis & Figure Export**:
   - Execute [`notebooks/03_final_analysis.ipynb`](notebooks/03_final_analysis.ipynb) to compute correlations, generate demographic plots, and export figure charts to [`reports/figures/`](reports/figures/).

---

## Key Insight Areas

- **User Perception & EMR Complexity**: Multi-level evaluation comparing rating of system complexity across medical professions.
- **Infrastructure Vulnerabilities**: Analysis of network outage frequency and backup power solutions across departments.
- **Technical Support & Training**: Turnover time for IT issue resolution vs. user attendance in HPRS training over 12 months.
- **Organizational Governance**: Correlation between facility action plans, supervisory monitoring, and staff confidence in EMR-based decision making.

---

## Environment & Requirements Setup

Requires Python 3.9+.

```bash
# Clone repository
git clone https://github.com/adamlawal/EMR_ANALYSIS.git
cd EMR_ANALYSIS

# Create virtual environment
python3 -m venv .venv
source .venv/bin/activate

# Install required packages
pip install -r requirements.txt
```
