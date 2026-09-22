# eda-task-5
# Healthcare Data Cleaning & Exploratory Analysis

This project prepares a healthcare admissions dataset for exploratory analysis. The accompanying Jupyter notebook loads the raw data, checks its structure and missing values, standardizes categorical fields, converts admission and discharge dates, and creates a length-of-stay feature.

## Overview

The notebook works with **1,000 patient admission records** and initially contains 10 columns. It focuses on establishing a clean, analysis-ready dataset before deeper visual or statistical exploration.

## Dataset fields

| Column | Description |
| --- | --- |
| `Patient_ID` | Unique patient record identifier |
| `Age` | Patient age |
| `Gender` | Patient gender |
| `Blood_Type` | Patient blood group |
| `Medical_Condition` | Recorded medical condition |
| `Medical_Code` | Code associated with the medical condition |
| `Date_of_Admission` | Admission date |
| `Discharge_Date` | Discharge date |
| `Admission_Type` | Type of admission: Emergency, Elective, or Urgent |
| `Billing_Amount` | Amount billed for the admission |

## What the notebook does

1. Loads `healthcare_data.csv` with pandas.
2. Inspects the first records, dataset dimensions, data types, and missing values.
3. Replaces missing `Medical_Code` values with `unknown` (30 records in the supplied data).
4. Cleans `Admission_Type` by removing extra spaces and applying consistent title casing.
5. Converts admission and discharge dates to datetime values.
6. Extracts admission year, month, and day when needed.
7. Creates `stay_days`, calculated as the difference between discharge and admission dates.

## Admission-type distribution

| Admission type | Records |
| --- | ---: |
| Emergency | 381 |
| Elective | 368 |
| Urgent | 251 |

## Getting started

### Requirements

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

### Run the notebook

1. Place `healthcare_data.csv` where the notebook can access it.
2. Update the path in the loading cell if necessary:

```python
df = pd.read_csv("healthcare_data.csv")
```

3. Open and run the notebook:

```bash
jupyter notebook eda5.ipynb
```

## Project structure

```text
.
├── eda5.ipynb             # Data cleaning and exploratory-analysis notebook
├── healthcare_data.csv    # Source dataset (add locally)
└── README.md
```

## Notes

- The current notebook is a data-preparation foundation. The imported plotting libraries (`matplotlib` and `seaborn`) can be used next for demographic, admission-type, billing, and length-of-stay visualizations.
- Treat the data as a learning or analytical dataset. Do not use it for clinical decisions or as a source of real patient information.

## License

Add a license that matches the source dataset's terms before publishing this project.
