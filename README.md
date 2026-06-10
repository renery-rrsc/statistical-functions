# Statistical Functions - Stats Weapons

A comprehensive Python utility library for statistical analysis, hypothesis testing, outlier detection, and data exploration.

## 📋 Overview

**Stats Weapons** is a powerful statistical analysis toolkit designed to simplify complex statistical computations and hypothesis testing. It provides a unified interface for data loading, descriptive statistics, hypothesis testing (parametric and non-parametric), outlier detection, correlation analysis, and probability distribution fitting.

**Author:** Renery Carvalho  
**Last Updated:** May 2, 2026  
**Email:** reneryroniery@gmail.com

## 🎯 Features

### Data Loading & Transformation
- **`extract_data()`** - Load data from multiple formats:
  - Spreadsheets: `.csv`, `.xls`, `.xlsx`, `.xlsm`
  - Databases: `.sql`, `.sqlite`, `.sqlite3`, `.db`
  - Other formats: `.json`, `.parquet`, `.feather`, `.pkl`, `.txt`, `.xml`, `.h5`, `.hdf5`
  - Support for SQL Server via `pyodbc` with authentication options
  - Automatic data type inference and basic validation

### Descriptive Analysis
- **`basic_statistics()`** - Comprehensive dataset overview:
  - Statistical summaries (mean, median, std, quantiles, etc.)
  - Data type analysis
  - Missing value detection
  - Correlation matrices
  - Univariate and multivariate visualizations
  - Distribution insights

### Normality Testing
- **`normality_tests()`** - Multiple normality test methodologies:
  - Shapiro-Wilk test
  - Kolmogorov-Smirnov test
  - Anderson-Darling test
  - D'Agostino-Pearson test
  - Jarque-Bera test
  - Lilliefors test
  - Visual Q-Q plots

### Correlation & Association
- **`correlation_analysis()`** - Relationship detection:
  - Pearson correlation (linear relationships)
  - Spearman correlation (monotonic relationships)
  - Kendall correlation (non-parametric)
  - Visualization and p-value reporting

### Outlier Detection
- **`outliers_detection()`** - Multiple outlier detection methods:
  - Z-score method
  - IQR (Interquartile Range) method
  - Isolation Forest
  - Local Outlier Factor (LOF)
  - One-Class SVM
  - DBSCAN clustering
  - Visual identification with boxplots

### Probability Distributions
- **`probability_distributions()`** - Distribution fitting and analysis:
  - Test data against multiple standard distributions
  - Goodness-of-fit metrics
  - Parameter estimation
  - Visual distribution comparisons

### Hypothesis Testing - Single Population
- **`test_population_mean()`** - Test population mean (t-test or z-test)
- **`test_population_proportion()`** - Test population proportion
- **`test_population_variance()`** - Test population variance (chi-square test)

### Hypothesis Testing - Two Populations
- **`test_2independent_mean()`** - Compare means of two independent samples
- **`test_2paired_mean()`** - Compare means of paired samples (paired t-test)
- **`test_2independent_proportion()`** - Compare proportions of two groups
- **`test_2population_variance()`** - Compare variances of two populations (F-test)

### Hypothesis Testing - Multiple Populations
- **`test_1way_anova()`** - One-way ANOVA for comparing multiple groups
  - Includes post-hoc Tukey HSD testing

### Non-Parametric Tests
- **`independent_mannwhitneyu()`** - Mann-Whitney U test for independent samples
- **`paired_wilcoxon()`** - Wilcoxon signed-rank test for paired samples
- **`independent_chisquare_test()`** - Chi-square test of independence
- **`independent_exact_fisher()`** - Fisher's exact test
- **`dependent_mcnemar()`** - McNemar's test for paired categorical data

## 📦 Installation

### Prerequisites
- Python 3.8 or higher
- pip package manager

### Setup

1. Clone or download the project files
2. Navigate to the project directory:
   ```bash
   cd statistical_functions
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## 📚 Dependencies

Core libraries:
- **pandas** (3.0.3) - Data manipulation and analysis
- **numpy** (2.4.6) - Numerical computing
- **scipy** (1.17.1) - Scientific computing and statistical tests
- **scikit-learn** (1.9.0) - Machine learning and outlier detection
- **statsmodels** (0.14.6) - Advanced statistical analysis
- **matplotlib** (3.10.9) - Data visualization
- **seaborn** (0.13.2) - Statistical data visualization
- **pyodbc** (5.3.0) - SQL Server connectivity

## 🚀 Quick Start

### Basic Usage

```python
from stats_weapons import extract_data, basic_statistics, normality_tests

# Load data from CSV
df = extract_data('data.csv')

# Get comprehensive statistics
stats_summary = basic_statistics(df)

# Test for normality
normality_results = normality_tests(df, methodology='all')
```

### Data Loading Examples

```python
# CSV file
df = extract_data('data.csv')

# Excel file
df = extract_data('data.xlsx', sheet_name='Sheet1')

# SQLite database
df = extract_data('database.db', table_name='my_table')

# SQL Server
df = extract_data(
    'query.sql',
    server='localhost',
    database='mydb',
    table_name='my_table',
    username='user',
    password='password'
)
```

### Hypothesis Testing Examples

```python
# Test if population mean equals 100
results = test_population_mean(sample_data, population_mean=100)

# Compare two independent samples
results = test_2independent_mean(sample1, sample2)

# One-way ANOVA
results = test_1way_anova([group1, group2, group3])

# Mann-Whitney U test (non-parametric)
results = independent_mannwhitneyu(sample1, sample2)
```

### Outlier Detection Examples

```python
# Detect outliers using Z-score
outliers = outliers_detection(df, methodology='z-score')

# Using Isolation Forest
outliers = outliers_detection(df, methodology='isolation_forest')

# Using Local Outlier Factor
outliers = outliers_detection(df, methodology='lof')
```

## 📁 Project Structure

```
statistical_functions/
├── stats_weapons.py       # Main statistical analysis module
├── requirements.txt       # Python package dependencies
├── README.md             # This file
├── carbon1.png           # Documentation/reference image
├── carbon2.png           # Documentation/reference image
└── sts/                  # Supplementary materials directory
```

## 🔍 Key Functions Reference

| Function | Purpose | Parameters |
|----------|---------|-----------|
| `extract_data()` | Load data from multiple formats | `file_path`, `**kwargs` |
| `basic_statistics()` | Comprehensive descriptive analysis | `df` |
| `normality_tests()` | Test for normal distribution | `df`, `methodology`, `alpha` |
| `correlation_analysis()` | Analyze relationships between variables | `df`, `target`, `methodology` |
| `outliers_detection()` | Identify outliers in data | `df`, `methodology` |
| `probability_distributions()` | Fit and test probability distributions | `data` |
| `test_population_mean()` | Single population mean test | `sample_data`, `population_mean`, `population_std`, `alpha` |
| `test_2independent_mean()` | Two independent samples mean test | `sample1`, `sample2`, `pop_std1`, `pop_std2`, `alpha` |
| `test_1way_anova()` | ANOVA for multiple groups | `samples`, `alpha` |
| `independent_mannwhitneyu()` | Non-parametric rank test | `sample1`, `sample2`, `alpha` |
| `independent_chisquare_test()` | Chi-square independence test | `contingency_table`, `alpha` |

## 📊 Output Format

Most functions return a comprehensive dictionary containing:
- **Test statistics** and **p-values**
- **Confidence intervals** (where applicable)
- **Effect sizes** and **assumptions checks**
- **Visual plots** (PNG files or matplotlib figures)
- **Interpretation** and **conclusions**

## ⚙️ Important Notes

1. **Automatic Column Dropping**: The `extract_data()` function automatically drops the first column of loaded data. This is intentional behavior for handling index columns.

2. **SQL Server Authentication**: For SQL Server connections, you can use either:
   - Windows authentication (`Trusted_Connection=yes`)
   - Username/password authentication

3. **Statistical Significance**: All hypothesis tests use `alpha=0.05` by default. Adjust this parameter based on your requirements.

4. **Two-tailed vs One-tailed**: Most tests support `alternative` parameter with options:
   - `'two-sided'` (default)
   - `'less'`
   - `'greater'`

## 🛠️ Data Types Supported

- Numeric types: `int`, `float`, `np.int64`, `np.float64`
- String types: Categorical data for contingency tables
- Pandas objects: `Series`, `DataFrame`
- Array-like: `list`, `np.ndarray`

## 📝 Usage Tips

1. **Data Preparation**: Ensure your data is clean and properly formatted before analysis
2. **Missing Values**: Handle missing values before statistical testing
3. **Assumptions**: Always verify statistical test assumptions before interpreting results
4. **Visualization**: Most functions include visualization outputs for better interpretation
5. **Effect Sizes**: Pay attention to effect sizes, not just p-values

## 🐛 Error Handling

The module includes comprehensive error handling for:
- Missing files
- Unsupported file formats
- Invalid database connections
- Malformed input data
- Missing required parameters

## 📞 Support

For issues, questions, or contributions:
- **Email:** reneryroniery@gmail.com
- **GitHub:** Check project repository for updates

## 📄 License

Developed and maintained by Renery Carvalho

---

**Version:** 1.0.0  
**Last Updated:** May 2, 2026
