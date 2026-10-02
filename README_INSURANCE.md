# Insurance Data Analysis & Feature Engineering

This project performs **exploratory data analysis (EDA), data cleaning, feature engineering, statistical feature selection, and numerical preprocessing** on an insurance-cost dataset.

The work is implemented in the Jupyter notebook [`insurance.ipynb`](insurance.ipynb).

## Project Overview

The analysis uses insurance customer information such as age, sex, BMI, number of children, smoking status, region, and medical charges.

### Dataset

- **File:** `insurance.csv`
- **Rows:** 1,338
- **Columns:** 7
- **Target variable:** `charges`

| Column | Description |
|---|---|
| `age` | Customer age |
| `sex` | Customer sex |
| `bmi` | Body Mass Index |
| `children` | Number of children/dependents |
| `smoker` | Smoking status |
| `region` | Geographic region |
| `charges` | Medical insurance charges |

## What the Notebook Does

### 1. Exploratory Data Analysis

The notebook examines:

- Dataset shape and sample records
- Data types and descriptive statistics
- Missing values
- Numeric distributions using histograms
- Category frequencies
- Outliers using box plots
- Numeric correlations using a heatmap

### 2. Data Cleaning & Preprocessing

The notebook:

- Creates a working copy of the dataset
- Removes duplicate rows
- Checks for missing values
- Encodes `sex` as a binary variable
- Encodes `smoker` as a binary variable
- Renames these variables to `is_female` and `is_smoker`
- Applies one-hot encoding to `region`

### 3. Feature Engineering

BMI is converted into categories using standard BMI thresholds:

- Underweight: `< 18.5`
- Normal: `18.5–24.9`
- Overweight: `25.0–29.9`
- Obese: `>= 30`

The categorical BMI feature is then one-hot encoded.

### 4. Feature Scaling

`StandardScaler` is applied to:

- `age`
- `bmi`
- `children`

### 5. Statistical Feature Analysis

The notebook uses:

- **Pearson correlation** to examine relationships between numerical features and `charges`.
- **Chi-square tests** to examine relationships between categorical features and binned insurance charges.

### 6. Final Feature Set

The notebook creates `final_df` containing the selected variables:

```text
age
is_female
bmi
children
is_smoker
charges
region_southeast
bmi_category_Obese
```

> **Note:** The current notebook performs analysis and preprocessing; it does not train or evaluate a machine-learning regression model.

## Technologies Used

- Python 3
- Jupyter Notebook
- NumPy
- Pandas
- Matplotlib
- Seaborn
- SciPy
- Scikit-learn

## Installation

Create and activate a Python environment, then install the required packages:

```bash
pip install numpy pandas matplotlib seaborn scipy scikit-learn jupyter
```

## How to Run

1. Clone or download the project.
2. Make sure `insurance.csv` and `insurance.ipynb` are in the same directory.
3. Start Jupyter Notebook:

```bash
jupyter notebook
```

4. Open `insurance.ipynb`.
5. Run the cells from top to bottom.

## Project Structure

```text
.
├── insurance.csv
├── insurance.ipynb
└── README_INSURANCE.md
```

## Expected Outcome

After running the notebook, you will have:

- An understanding of the dataset's structure and distributions
- Cleaned and encoded insurance data
- Engineered BMI-category features
- Scaled numerical variables
- Pearson correlation results
- Chi-square feature-selection results
- A reduced `final_df` prepared for a potential downstream machine-learning task

## Notes

- The notebook suppresses Python warnings for cleaner output.
- The source CSV is expected to remain unchanged; preprocessing is performed on a DataFrame copy.
- The notebook contains exploratory visualizations, so running it in Jupyter will generate plots.

## Author / Project

This README documents the analysis contained in the supplied project notebook.
