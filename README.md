# Bank Account Fraud Detection

Data analysis and bank fraud detection project using exploratory data analysis and data visualization techniques.

##  Description

This project aims to analyze a banking transactions dataset to identify fraud patterns and understand the factors that contribute to fraudulent activities. The project uses Python data analysis techniques to clean, explore, and visualize fraud data.

##  Dataset

The Fraud_Detection.csv dataset contains:
- 1,000,000 entries with 32 columns of features
- Target variable: "fraud_bool" (fraud indicator: 0 = legitimate, 1 = fraud)
- Features including: income, age, banking history, risk scores, payment type, employment status, etc.

##  Technologies Used

- Python 3
- Pandas: Data manipulation and analysis
- NumPy: Numerical computations
- Matplotlib: Data visualization
- SciPy: Scientific computations
- Jupyter Notebook: Interactive development environment

##  Project Structure

```
Bank Account Fraud/
│
├── data/
│   └── Fraud_Detection.zip  # You need to extract it after cloning the repo to get access to the main data
│
├── project.ipynb                 # Main notebook containing the analysis
│
└── README.md                     # Project documentation
```

##  Analysis Steps

### 1. Loading and Initial Inspection
- Dataset loading
- Preview of the first rows
- Structure analysis (shape, info, describe)
- Checking for missing and duplicated values
- Class distribution analysis (fraud vs. non-fraud)

### 2. Data Cleaning
- Replacing `-1` values with `NaN`
- Filtering customers under 18 years old
- Handling missing values:
  - Creating binary markers (`has_prev_address`, `has_bank_history`)
  - Replacing missing values with median for certain columns
- Removing unnecessary columns (constant values)

### 3. Exploratory Analysis
- Correlation analysis: Identifying variables most correlated with fraud
- Creating analytical metrics:
  - `client_risk_score`: Composite client risk score
  - Age groups for segmented analysis
- Visualizations:
  - Bar chart: Fraud rate by age group
  - Heatmap: Correlation between key variables
  - Scatter plots: Two-dimensional analysis (risk score vs. credit limit)
  - Analysis of textual factors (employment status, housing, payment type)

### 4. Key Insights

#### Variables Increasing Fraud Risk:
- `credit_risk_score` (correlation: 0.071)
- `proposed_credit_limit` (correlation: 0.069)
- `customer_age` (correlation: 0.063)
- `income` (correlation: 0.045)

#### Variables Reducing Risk:
- `keep_alive_session` (correlation: -0.051)
- `has_prev_address` (correlation: -0.049)
- `date_of_birth_distinct_emails_4w` (correlation: -0.044)

## Installation and Usage

### Prerequisites
#extraction
You need to extract `Fraud_Detection.zip` it after cloning the repo to get access to the main data
```bash
pip install pandas numpy matplotlib scipy jupyter
```

### Running the Project

1. Clone or download the project
2. Open the Jupyter notebook:

```bash
jupyter notebook project.ipynb
```

3. Run the cells in order to reproduce the analysis

### Important Note

Make sure the `Fraud_Detection.csv` file is located in the `data/` folder so the code can load it correctly.

##  Results and Visualizations

The project generates several key visualizations:
- Fraud rate analysis by age group
- Correlation heatmap between important variables
- Scatter plots comparing legitimate and fraudulent customers
- Analyses by employment status, housing, and payment type

##  Created Metrics

### Client Risk Score
Composite score based on:
- `high_income_flag`: Income above median
- `new_client_flag`: Recent client (fewer banking months than median)
- `high_credit_risk_flag`: High credit risk score

### Age Groups
- <= 25 years
- 26-35 years
- 36-50 years
- 50+ years
## Notes

- The dataset contains missing values represented by `-1` which were converted to `NaN`
- The class distribution is imbalanced (few fraud cases)
- The analysis reveals that customers without previous address history have a higher fraud rate

##  Author

Bank fraud detection data analysis project.

##  License

This project is provided for educational and analysis purposes.
