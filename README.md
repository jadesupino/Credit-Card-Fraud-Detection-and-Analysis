# Credit-Card-Fraud-Detection-and-Analysis

## Overview
This project analyzes and detects fraudulent credit card transactions using Python, SQL, and Power BI. It integrates rule-based detection, machine learning, and interactive visualizations to identify anomalous patterns in transaction behavior, including unusual amounts, times, locations, and transaction frequency.

## Key Metrics
- Identify high-risk transactions and users
- Generate actionable insights for fraud prevention
- Enable dynamic exploration of fraud trends for stakeholders

## Tools & Technologies
- Python: Data generation, preprocessing, analysis, and machine learning
    - Faker: Generate fake data
    - random, csv, os, datetime: For logic and file handling
    - NumPy, Pandas: Data manipulation and analysis
    - scikit-learn (Random Forest) - for machine learning
- SQL: Rule-based detection queries
- PowerBI: Interactive dashboard and visualizations

## Dataset Generation
- Python script: *transaction_dataset_creation.py*
- Dataset: *transaction_dataset.csv* with 1,000 transactions
  - Fields include:
    - transaction_id (INT): Auto-incremented identifier
    - user_id (INT): Randomizer user reference
    - date (DATETIME): Random timestamp
    - amount (FLOAT): Transaction amount
    - category (STR): Merchant category from a pre-defined list
    - location (STR): Random popular U.S. cities from a pre-defined list

## Rule-Based Fraud Detection (SQL)
The following rules were applied to flag potentially fraudlent transactions:
1. High-Value Transactions: Amount > $10,000
2. Suspicious Time Window: Transactions between 2 AM - 5 AM
3. Geographic Anomalies: Users with transactions in > 6 unique locations
4. Transaction Velocity: >= 5 transactions per hour per user
- SQL queries update IsFraud (BOOLEAN) and FraudReason (VARCHAR) columns
- Updated Dataset: *transactions_updated.csv*

## Machine Learning Fraud Detection
- Model: Random Forest classifier
- Features: One-hot encoded categorical features, transaction amount, time, and location
- Python Script: *fraud_detector.py*
- Functionality: Predicts whether new transactions are fraudulent
- Performance is evaluated using standard metrics with an adjustable threshold
- Demonstrates detection on unseen transactions

## Data Analysis & Visualizations (Power BI)
1. Fraudulent vs. Legitimate Transactions: Donut chart by fraud reason
2. Top 10 Fraud Locations: Bar chart showing high-risk cities and merchant categories
3. Total Fraud Cases by Reason: Bar chart identifying common fraud patterns  
4. Timeline of Fraudulent Spending: Line chart showing seasonal trends
- Key Insights:
  - 11% of fraud occurs between 2 - 5 AM
  - High-value transactions and rapid transaction frequency highlight potential misuse

## Dashboard Preview
### Default View
This view displays the dashboard upon initial load.

![Default Dashboard View](images/dashboard.jpg)

## Project Files
- *transaction_dataset_creation.py*: Python dataset generator
- *transaction_dataset.csv*: Initial synethic dataset
- *transactions_updated.csv*: Dataset with fraud labels
- *fraud_rules.sql*: SQL queries for rule-based fraud detection
- *fraud_detector.py*: Machine learning-based fraud detection script
- *PowerBI_dashboard*: Interactive fraud dashboard
- *dashboard.pdf*: Static Power BI report

## Conclusion ##
This project demonstrates end-to-end fraud detection using data analytics, SQL rules, machine learning, and interactive visualizations. By integrating these methods, it identifies suspicious financial activity and provides stakeholders with actionable insights to monitor and mitigate credit card fraud effectively.
