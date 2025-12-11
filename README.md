# Messy Retail Audit Analysis

A comprehensive data analysis and machine learning project analyzing retail data from a Sample Superstore dataset. This project demonstrates data cleaning, exploratory data analysis (EDA), and predictive modeling techniques.

## Project Overview

This analysis addresses a real-world scenario where raw CSV data from a legacy retail system contains mixed data types, missing value markers, and formatting inconsistencies. The project applies best practices in data cleaning, visualization, and statistical modeling.

## Dataset

- **Source**: Sample Supermarket Dataset (bravehart101/sample-supermarket-dataset)
- **Location**: `../datasets/bravehart101/sample-supermarket-dataset/versions/1/SampleSuperstore.csv`
- **Size**: Multiple rows with 21+ columns

## Column Descriptions

| Column | Type | Description |
|--------|------|-------------|
| Sales | Numeric | Revenue from transactions |
| Profit | Numeric | Net profit from sales |
| Quantity | Numeric | Number of items sold |
| Discount | Numeric | Discount percentage applied |
| Ship Mode | Categorical | Shipping method (e.g., Same Day, Standard) |
| Segment | Categorical | Customer segment (Consumer, Corporate, Home Office) |
| Region | Categorical | Geographic region |
| Category | Categorical | Product category (Furniture, Office Supplies, Technology) |
| Sub-Category | Categorical | Detailed product subcategory |
| State | Categorical | U.S. state |
| City | Categorical | City location |
| Country | Categorical | Country (USA) |
| Postal Code | Categorical | Postal code |

## Notebook Sections

### Section 1: Introduction & Setup
- Project overview and objectives
- Data loading and initial inspection

### Section 2: Data Exploration
- Dataset shape and size analysis
- Data types and missing value detection
- Descriptive statistics for numeric and categorical variables
- Unique value counts and distributions

### Section 3: Data Quality & Cleaning
- Duplicate record detection and removal
- Outlier detection using IQR (Interquartile Range) method
- Sales and Profit outlier visualization and removal
- Data quality before/after comparisons

### Section 4: Exploratory Data Analysis (EDA)
- Statistical summaries and correlations
- Correlation heatmap for numeric features
- Distribution analysis by categorical features:
  - Quantity and Discount boxplots
  - Category vs Sales relationships
  - Segment, Region, and Sub-Category performance
- Profit analysis by dimensions:
  - Average profit by category, segment, region, and subcategory
  - Total profit contributions

### Section 5: Predictive Modeling
- **Model**: Linear Regression
- **Features**: Sales, Discount, Quantity
- **Target**: Profit
- **Train-Test Split**: 80-20 split with random_state=42
- **Evaluation Metrics**: 
  - R² Score (coefficient of determination)
  - RMSE (Root Mean Squared Error)
- **Output**: Feature coefficients showing impact of each variable on profit

## Key Findings

### Outlier Detection
- Uses IQR method: bounds defined as Q1 - 1.5×IQR and Q3 + 1.5×IQR
- Identifies extreme values in Sales and Profit columns
- Removes outliers while preserving distribution analysis

### Performance Insights
- Analyzes profit and sales performance across:
  - Product categories
  - Customer segments
  - Geographic regions
  - Product subcategories

### Model Insights
- Linear regression coefficients reveal:
  - How Sales, Discount, and Quantity influence Profit
  - Relative importance of each feature

## Technologies Used

- **Python 3.x**
- **pandas**: Data manipulation and analysis
- **matplotlib**: Visualization
- **seaborn**: Statistical data visualization
- **scikit-learn**: Machine learning and model evaluation
- **numpy**: Numerical computations

## How to Run

1. **Prerequisites**: Install required packages
   ```bash
   pip install pandas matplotlib seaborn scikit-learn numpy
   ```

2. **Execute Notebook**: Open `Messy Retail Audit.ipynb` in Jupyter and run cells sequentially

3. **Expected Output**:
   - Data summary statistics
   - Visualizations (boxplots, bar charts, heatmaps)
   - Model evaluation metrics
   - Feature coefficients

## Key Techniques Demonstrated

### Data Cleaning
- Duplicate removal
- Missing value analysis
- Outlier detection and handling

### Exploratory Data Analysis
- Univariate analysis (distributions, summary stats)
- Bivariate analysis (relationships between variables)
- Correlation analysis
- Group-by aggregations

### Visualization
- Boxplots for distribution analysis
- Bar charts for categorical comparisons
- Correlation heatmaps
- Before/after comparisons

### Machine Learning
- Feature selection
- Model training with train-test split
- Model evaluation and interpretation
- Coefficient analysis

## Insights & Recommendations

1. **Data Quality**: Removing outliers improves model interpretability
2. **Feature Impact**: Each feature's coefficient shows its effect on profit
3. **Business Value**: Performance analysis identifies high-profit segments and regions
4. **Future Work**: Consider non-linear models, additional features, or time-series analysis

## File Structure

```
Messy Retail Audit/
├── README.md                          # This file
├── Messy Retail Audit.ipynb          # Main analysis notebook
└── datasets/
    └── bravehart101/sample-supermarket-dataset/
        └── versions/1/
            └── SampleSuperstore.csv   # Source data
```

## Notes

- The analysis assumes data is loaded from a relative path structure
- Models use random_state=42 for reproducibility
- Visualizations are generated inline in the notebook
- All percentages and calculations are relative to total profit/sales

## Author Notes

This project serves as a comprehensive template for:
- Real-world data cleaning scenarios
- EDA best practices
- Communication of data insights through visualizations
- Applied machine learning for business analytics
