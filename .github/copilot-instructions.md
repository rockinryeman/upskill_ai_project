# Copilot Instructions for Data Analysis Project

## Project Overview
This is a data analysis project using Jupyter notebooks for exploratory data analysis, visualization, and statistical modeling. The project follows a structured approach to data science workflows.

## Key Architecture Patterns

### Notebook Structure
- **Cell 1**: Always markdown header explaining the analysis purpose
- **Cell 2**: Import all required libraries with version printing for reproducibility
- **Cell 3+**: Follow the pattern: load data → explore → visualize → model → export
- Use `warnings.filterwarnings('ignore')` to keep outputs clean
- Set consistent plotting style with `plt.style.use('default')` and `sns.set_palette("husl")`

### Data Handling Conventions
- Generate reproducible sample data using `np.random.seed(42)`
- Always validate data constraints (e.g., `np.maximum(df['sales'], 0)` for non-negative values)
- Use pandas datetime ranges for time series: `pd.date_range('2024-01-01', periods=1000, freq='D')`
- Create realistic synthetic data with seasonal patterns using sine waves

### Visualization Standards
- Use subplots for multiple related charts: `fig, axes = plt.subplots(2, 2, figsize=(15, 10))`
- Include descriptive titles for all plots
- Always call `plt.tight_layout()` before `plt.show()`
- Use `alpha=0.5` for scatter plots to handle overlapping points
- Combine multiple chart types: line plots for time series, bar charts for categories, scatter for correlations

### Code Organization
- Group imports at the top with version checks for debugging
- Use descriptive variable names that match business context (`sales`, `marketing_spend`, `region`)
- Print confirmation messages after major operations
- Include summary statistics with `df.describe()` after data generation

## Development Workflow
- Run cells sequentially to maintain state consistency
- Always check data shapes and types after transformations
- Use `df.head()` to preview data after generation or modification
- Combine statistical analysis with visual exploration

## Common Patterns to Follow
```python
# Standard library import block
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from datetime import datetime, timedelta
import warnings
warnings.filterwarnings('ignore')

# Plotting setup
plt.style.use('default')
sns.set_palette("husl")
```

## File References
- Main analysis notebook: `Robin_Test.ipynb` - Complete data analysis workflow
- Follow the 4-cell pattern: header → imports → data generation → visualization