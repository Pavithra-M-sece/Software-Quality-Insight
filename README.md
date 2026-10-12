# Software Quality Insight

**DS Sprint – Use Case 28 | CodeMetric Software Labs**

## 📌 Project Overview

Software defects can affect product reliability, customer satisfaction, and development costs. Identifying the software metrics associated with a higher number of defects helps development teams improve code quality and prioritize testing efforts.

The **Software Quality Insight** project analyzes software modules, development activity, code complexity, and test coverage to identify patterns associated with defects. It also applies machine learning techniques to estimate defect counts and support data-driven software quality decisions.

## 🎯 Business Problem

**Which software metrics are associated with modules having more defects?**

The project investigates whether metrics such as code complexity, coupling, code churn, test coverage, module size, commit activity, and contributor count are associated with higher defect counts.

## 🎯 Project Objectives

- Understand and clean software quality datasets.
- Identify missing values, duplicate records, inconsistent module names, and potential outliers.
- Perform exploratory data analysis (EDA) to discover defect patterns.
- Create useful features for software quality analysis.
- Build and evaluate machine learning models to predict defect counts.
- Present actionable recommendations for improving software quality.

## 📂 Dataset Description

The project uses five CSV datasets.

| Dataset | Description |
|---|---|
| `modules.csv` | Module information, component, programming language, and size |
| `metrics.csv` | Code complexity, coupling, churn, and test coverage |
| `defects.csv` | Defect count, severity, and release information |
| `commits.csv` | Commit count, contributors, and changed lines |
| `releases.csv` | Release dates, version information, and module details |

The datasets are combined using appropriate module and release identifiers. The actual data should be checked to confirm that these identifiers are consistent across all files.

## 🛠️ Tools and Technologies

- **Python** – Data cleaning, analysis, feature engineering, and modeling
- **Google Colab / Jupyter Notebook** – Notebook execution
- **Pandas and NumPy** – Data manipulation
- **Matplotlib and Seaborn** – Data visualization
- **Scikit-learn** – Machine learning and model evaluation
- **Excel** – Formula-based analysis, PivotTables, and charts
- **Git and GitHub** – Version control and project sharing

## 📁 Project Structure

```text
Software-Quality-Insight/
│
├── data/
│   ├── raw/
│   │   ├── modules.csv
│   │   ├── metrics.csv
│   │   ├── defects.csv
│   │   ├── commits.csv
│   │   └── releases.csv
│   │
│   └── processed/
│       ├── software_quality_cleaned.csv
│       └── software_quality_engineered.csv
│
├── notebooks/
│   ├── 01_data_understanding_and_cleaning.ipynb
│   ├── 02_eda_and_feature_engineering.ipynb
│   └── 03_machine_learning_and_evaluation.ipynb
│
├── excel/
│   └── software_quality_analysis.xlsx
│
├── presentation/
│   └── software_quality_insight_presentation.pptx
│
├── outputs/
│   ├── model_performance.csv
│   ├── predictions.csv
│   └── feature_importance.csv
│
├── requirements.txt
└── README.md
```

*Note: This is the suggested folder structure. Include files and folders as you create them, and update the names if your repository uses a different structure.*

## 🔄 Project Workflow

### 1. Data Understanding and Cleaning

The five datasets are inspected to understand their structure, data types, missing values, and duplicate records.

Data preparation includes:

- Standardizing module names.
- Converting numeric columns to suitable data types.
- Handling duplicate module and release records.
- Identifying extreme complexity values for review.
- Checking unmatched module and release records.
- Handling missing metric values.
- Combining datasets into a module-release-level analysis table.

**Output:** `software_quality_cleaned.csv`

### 2. Exploratory Data Analysis and Feature Engineering

EDA is used to explore relationships between software metrics and defects.

Analysis includes:

- Defect counts by module and component.
- Defect severity distribution.
- Complexity versus defect count.
- Code churn versus defect count.
- Test coverage versus defect count.
- Correlation analysis of numeric metrics.
- Defect trends across releases.
- Commit activity and contributor patterns.

Feature engineering may include:

- Coverage gap.
- Churn per commit.
- Changed lines per commit.
- Complexity risk categories.
- Repeated-defect indicators for exploratory analysis.

**Output:** `software_quality_engineered.csv` and visualizations.

### 3. Machine Learning and Evaluation

A regression approach is used to estimate defect counts.

The notebook compares:

- **Dummy Regressor:** A simple baseline that predicts the mean defect count.
- **Random Forest Regressor:** A model that can capture nonlinear patterns and interactions between metrics.

The target variable is:

`defect_count`

Potential input features include complexity, coupling, churn, test coverage, size, programming language, component, commit count, contributor count, changed lines, and release.

Target-derived features, such as total defects calculated from the complete dataset, must be excluded from model inputs to avoid data leakage.

Model evaluation uses:

- **MAE (Mean Absolute Error):** Average absolute prediction error.
- **RMSE (Root Mean Squared Error):** Error measure that penalizes larger mistakes more heavily.
- **R² Score:** Measures how much target variation is explained by the model relative to a mean baseline.

**Outputs:** Model performance metrics, predictions, and feature importance.

### 4. Excel Analysis

Excel is used to summarize findings in a business-friendly format.

The workbook may include:

- Cleaned data.
- Formula-based calculations.
- PivotTables summarizing defects by module, component, and release.
- Charts showing defect distributions and metric relationships.
- A summary dashboard highlighting important observations.

### 5. Business Insights and Recommendations

The final presentation summarizes the strongest patterns found in the actual data and translates them into practical recommendations for software development and testing teams.

## 📊 Expected Deliverables

1. Cleaned software quality dataset.
2. Python notebook for data understanding and cleaning.
3. Python notebook for EDA and feature engineering.
4. Python notebook for machine learning and evaluation.
5. Excel analysis workbook with formulas, PivotTables, and charts.
6. Short presentation with business insights and recommendations.
7. GitHub repository containing project documentation and relevant files.

## ▶️ How to Run the Project

### Option 1: Google Colab

1. Upload the notebooks to Google Colab.
2. Upload the five input CSV files or a ZIP containing them when prompted.
3. Run `01_data_understanding_and_cleaning.ipynb` first.
4. Save the generated cleaned dataset.
5. Run `02_eda_and_feature_engineering.ipynb` using the cleaned dataset.
6. Save the engineered dataset.
7. Run `03_machine_learning_and_evaluation.ipynb` using the engineered dataset.
8. Download the resulting CSV files, charts, and model evaluation outputs.

Run the notebooks in order because each stage depends on the outputs of the previous stage.

### Option 2: Local Python Environment

Clone the repository:

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd Software-Quality-Insight
```

Install the required libraries:

```bash
pip install -r requirements.txt
```

Open the notebooks:

```bash
jupyter notebook
```

Run the notebooks in the following order:

1. `01_data_understanding_and_cleaning.ipynb`
2. `02_eda_and_feature_engineering.ipynb`
3. `03_machine_learning_and_evaluation.ipynb`

Ensure the CSV files are available in the paths expected by the notebooks.

## 📦 Requirements

Create a `requirements.txt` file with the following packages:

```text
pandas
numpy
matplotlib
seaborn
scikit-learn
jupyter
openpyxl
```

Google Colab usually includes many of these packages already.

## 📈 Key Findings

Record your findings here after running the notebooks on the actual dataset.

- **Module with the most defects:** Add the module name and defect count from the analysis.
- **Metric most strongly associated with defects:** Add the metric and its observed correlation or other supporting evidence.
- **Model performance:** Report the measured MAE, RMSE, and R² score.
- **Important predictors:** List the metrics identified by the fitted model, while noting that feature importance does not establish causation.

Do not fill in these results until the analysis has been executed.

## 💡 Business Recommendations

Based on the evidence produced by the analysis, the organization can consider the following actions:

- Prioritize code review and testing for modules with repeated or high-severity defects.
- Investigate high-complexity and high-churn modules if the data shows that they are associated with more defects.
- Review test coverage in modules with recurring defects.
- Monitor defect trends across releases to identify regressions.
- Use model predictions as a prioritization aid, not as a replacement for engineering judgment.
- Reassess the analysis as new release and defect data becomes available.

These recommendations should be refined to reflect the actual results.

## ⚠️ Limitations

- Associations between metrics and defects do not prove causation.
- Missing values, inconsistent identifiers, and small sample sizes can affect results.
- Defect counts may differ because of reporting practices or release-specific behavior.
- Random train-test splits can overestimate performance when the same modules appear in both sets across releases.
- Feature importance indicates predictive usefulness within the fitted model, not causal impact.
- Results depend on dataset quality and the representativeness of the available records.

## 👥 Project Information

- **Project:** Software Quality Insight
- **Sprint:** DS Sprint – Use Case 28
- **Organization:** CodeMetric Software Labs
- **Primary business question:** Which software metrics are associated with modules having more defects?

## 📜 License

Add the appropriate license if you intend to distribute this project publicly. If no license has been selected, specify that the repository is shared for educational or assessment purposes.

---

**Note:** This project is intended to support software quality analysis and decision-making. All conclusions and model performance figures should be based on the results obtained by running the notebooks on the project datasets.
