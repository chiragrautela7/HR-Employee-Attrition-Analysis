# HR Employee Attrition Analysis

## Project Overview

This project analyzes employee attrition data to identify workforce patterns associated with employee turnover.

The goal is not only to calculate an attrition percentage, but to answer practical HR questions around:

- overtime
- department
- job role
- salary level
- tenure
- income
- distance from home
- employee satisfaction

## Objective

To identify key patterns associated with employee attrition and convert the findings into actionable HR recommendations.

## Dataset

- Records: 2,520
- Raw columns: 31
- Cleaned columns: 30
- Target variable: `Attrition`
- Raw dataset: `data/HR_Employee_Attrition_RAW.csv`
- Cleaned dataset: `data/HR_Employee_Attrition_CLEANED.csv`

The raw dataset is intentionally kept unchanged so the cleaning process is reproducible.

## Project Workflow

### Phase 1 — Raw Data Understanding

The notebook first inspects:

- first rows
- shape
- column names
- data types
- statistical summary
- missing values
- duplicate records
- important categorical values

No cleaning is performed in Phase 1.

### Phase 2 — Data Cleaning

The cleaning process includes:

1. Duplicate check and removal if required
2. Removal of the technical `EmployeeNumber` field
3. Standardization of known categorical inconsistencies
4. Missing categorical values → `Unknown`
5. Missing numeric values → median
6. Safe handling of mixed `JoiningDate` formats
7. Numeric dtype validation
8. HR logical consistency checks
9. Final data-quality validation
10. Saving the cleaned CSV

### EDA

The analysis includes:

- overall attrition distribution
- attrition rate by department
- attrition rate by overtime
- attrition rate by salary slab
- top job roles by attrition rate
- years at company vs attrition
- monthly income vs attrition
- distance from home vs attrition

## Key Findings

- Overall attrition rate is approximately **12.1%**.
- Employees with overtime have a higher attrition rate than employees without overtime.
- Human Resources has the highest department-level attrition rate in this dataset.
- Several finance and HR roles show relatively high attrition rates.
- Employees who left have lower average tenure at the company than employees who stayed.
- Distance from home is slightly higher on average among employees who left.
- Salary slab by itself does not show a simple linear relationship with attrition.

These findings describe associations in the dataset and should not be interpreted as proof of causation.

## Business Recommendations

- Review overtime workload in teams with elevated attrition.
- Investigate retention challenges in higher-risk departments and roles.
- Strengthen onboarding, mentoring, and career development for newer employees.
- Use multiple workforce indicators together rather than relying on salary or overtime alone.
- Monitor attrition metrics regularly with consistent data-quality checks.

## Tools & Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

## Repository Structure

```text
HR_Employee_Attrition_Analysis/
│
├── data/
│   ├── HR_Employee_Attrition_RAW.csv
│   └── HR_Employee_Attrition_CLEANED.csv
│
├── notebooks/
│   └── HR_Employee_Attrition_Analysis.ipynb
│
├── visualizations/
│   ├── 01_attrition_distribution.png
│   ├── 02_attrition_rate_by_department.png
│   ├── 03_attrition_rate_by_overtime.png
│   ├── 04_attrition_rate_by_salary_slab.png
│   ├── 05_top_job_roles_attrition.png
│   ├── 06_years_at_company_by_attrition.png
│   ├── 07_monthly_income_by_attrition.png
│   └── 08_distance_from_home_by_attrition.png
│
├── README.md
└── requirements.txt
```

## How to Run

1. Clone or download the repository.
2. Install the required packages:

```bash
pip install -r requirements.txt
```

3. Open the notebook:

```text
notebooks/HR_Employee_Attrition_Analysis.ipynb
```

4. Run the notebook from top to bottom.

## Important Data-Cleaning Note

`JoiningDate` contains multiple valid date representations. The notebook handles the known formats explicitly instead of using a blind date conversion that could turn valid dates into missing values.

## Author

Data Analytics Portfolio Project
