# Retail-Customer-Churn-Prediction
An end-to-end Data Science project — from raw retail transactions to a machine learning churn predictor and interactive dashboard.

# Project Overview
This project analyzes 1,067,371 retail transactions from the Online Retail II UCI dataset to identify customers at risk of churning, extract business insights using SQL, and visualize findings through an interactive HTML dashboard.
Business Problem: A UK-based online retailer wants to identify which customers are likely to stop purchasing, so they can proactively target them with win-back campaigns.

# Key Results
MetricValueTotal Customers Analyzed5,878Churn Rate50.8% (2,985 customers)Model Accuracy69%ROC-AUC Score0.7481High Risk Customers2,606Peak Monthly Revenue£1.46M (Nov 2011)

## 🗂️ Project Structure

```
retail-churn-project/
│
├── data/
│   ├── online_retail_II.csv              # Raw dataset (Kaggle)
│   ├── customer_churn_features.csv       # Engineered features + churn labels
│   ├── churn_by_country.csv              # SQL query result
│   ├── risk_segments.csv                 # SQL query result
│   └── monthly_revenue.csv              # SQL query result
│
├── notebooks/
│   ├── 01_data_cleaning.ipynb            # Data cleaning + churn labeling
│   └── 02_sql_analysis.ipynb             # SQL business insights
│
├── dashboard/
│   └── churn_dashboard.html              # Interactive HTML dashboard
│
└── README.md
```

# Project Pipeline
Raw CSV (1M+ rows)
       ↓
  Python (Pandas)
  • Remove nulls & cancelled orders
  • Feature engineering (RFM)
  • Churn labeling (90-day rule)
       ↓
  SQL (SQLite)
  • Churn rate by country
  • Revenue trends
  • Risk segment analysis
  • Recovery target identification
       ↓
  Machine Learning (scikit-learn)
  • Random Forest Classifier
  • 69% Accuracy | 0.74 AUC
  • Churn probability scores
       ↓
  Interactive Dashboard (HTML + Chart.js)
  • KPI cards
  • Revenue trend line chart
  • Risk segment donut chart
  • Country churn bar chart

# Dashboard Preview

Open dashboard/churn_dashboard.html in any browser — no installation needed.

The dashboard includes:

5 KPI Cards — Customers, Churn Rate, High Risk Count, Peak Revenue, AUC Score
Monthly Revenue Trend — Line chart (Dec 2009 – Dec 2011)
Risk Segment Distribution — Donut chart (Low / Medium / High)
Churn Rate by Country — Top 10 markets
Avg Spend by Segment — Behavioral comparison
Recovery Targets Table — High-value churned customers with recommendations


# Machine Learning
Features Used
FeatureDescriptionFrequencyNumber of unique ordersMonetaryTotal amount spentAvgOrderValueAverage spend per orderTotalItemsTotal quantity purchasedUniqueProductsNumber of distinct productsUniqueCountriesCountries ordered from
Model Performance
Classification Report:
              precision    recall  f1-score
  Active (0)       0.71      0.64      0.67
 Churned (1)       0.67      0.73      0.70
    Accuracy                           0.69

ROC-AUC Score: 0.7481
Churn Definition
A customer is labeled churned if their last purchase was more than 90 days before the dataset snapshot date.

# Key Business Insights

Loyalty Gap — Low Risk customers spend 5.4× more (£5,009) than High Risk customers (£932)
Seasonal Peak — Revenue spikes every November; campaigns should launch in September
Recovery Priority — Customer 15098 spent £39,917 with 91% churn probability — urgent outreach needed
One-time buyers churn fastest — Customers with Frequency = 1 have the highest churn probability


# Business Recommendations

- Win-back campaign for top 10 high-value churned customers (£34K–£77K spend)
- Day-45 discount trigger for customers who haven't reordered after 45 days
- Focus retention on UK — 5,350 customers, highest absolute churn volume
- Bundle offers for one-time buyers to increase Frequency score


# Tech Stack
ToolPurposePython (Pandas)Data cleaning & feature engineeringSQLiteBusiness insight queriesscikit-learnRandom Forest modelHTML + Chart.jsInteractive dashboardGoogle ColabDevelopment environment

# Dataset
Online Retail II UCI — Available on Kaggle

1,067,371 transactions
8 columns: Invoice, StockCode, Description, Quantity, InvoiceDate, Price, Customer ID, Country
Date range: December 2009 – December 2011


# Author - Abhishek
