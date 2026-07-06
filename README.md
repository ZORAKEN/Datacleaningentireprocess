# Data Cleaning, Formatting & Business Analytics

## Project Overview

This project focuses on transforming raw customer and sales data into a clean, structured, and analysis-ready dataset. The workflow includes comprehensive data quality checks, preprocessing, customer funnel analysis, sales performance evaluation, and customer segmentation to generate actionable business insights.

---

### Data Quality Function

```python
def data_quality_check(df):
    quality_report = {
        'total_records': len(df),
        'duplicate_rows': df.duplicated().sum(),
        'missing_values': df.isnull().sum().to_dict(),
        'invalid_emails': df[
            ~df['email'].str.contains('@', na=False)
        ].shape[0],
        'invalid_ages': df[
            (df['age'] < 0) | (df['age'] > 120)
        ].shape[0]
    }
    return quality_report

quality_report = data_quality_check(df)
print(quality_report)
```

### Cleaning Process

After identifying quality issues, the dataset is cleaned by:

* Removing duplicate records
* Handling missing values using appropriate imputation or removal techniques
* Correcting invalid data formats
* Standardizing text fields
* Validating numerical ranges
* Ensuring consistent date formats
* Removing unnecessary columns
* Converting data types for efficient analysis
---

# Customer Funnel Analysis

Customer funnel analysis evaluates how customers progress through different stages of the sales journey.

Typical funnel stages include:

1. Website Visit
2. Product View
3. Add to Cart
4. Checkout
5. Purchase

### Funnel Metrics

* Total visitors
* Conversion rate
* Cart abandonment rate
* Purchase completion rate
* Drop-off percentage between funnel stages

This analysis helps identify bottlenecks and opportunities to improve customer conversion.
---

# Sales Performance Analysis

Sales performance analysis measures the effectiveness of products, regions, and sales strategies.

Key metrics include:

* Revenue growth
* Sales trends over time
* Best-selling products
* Lowest-performing products
* Profitability analysis
* Sales by category
* Sales by customer segment
* Repeat purchase rate
* Average customer spend
---

# Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Jupyter Notebook

---

# Project Workflow

```
Raw Dataset
      │
      ▼
Data Quality Check
      │
      ▼
Data Cleaning
      │
      ▼
Data Formatting
      │
      ▼
Exploratory Data Analysis
      │
      ▼
Customer Funnel Analysis
      │
      ▼
Sales Analysis
      │
      ▼
Sales Performance Analysis
      │
      ▼
Customer Segmentation
      │
      ▼
Business Insights & Visualization
```

This workflow ensures that raw data is transformed into high-quality, analysis-ready information, enabling accurate reporting, effective customer segmentation, improved sales performance evaluation, and data-driven business decision-making.
