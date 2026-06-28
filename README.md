# 🛍️ SQL Customer Retention Strategy
### Decoding Customer Value for a D2C Fashion Brand

![Python](https://img.shields.io/badge/Python-3.11-blue)
![SQL](https://img.shields.io/badge/MySQL-8.0-orange)
![PowerBI](https://img.shields.io/badge/Power_BI-Dashboard-yellow)
![Pandas](https://img.shields.io/badge/Pandas-Data_Analysis-green)

---

## 📋 Project Overview

A Direct-to-Consumer (D2C) fashion brand sells clothing,
accessories, footwear and outerwear across the United States.
The brand has 3,900 customers and runs promotional discount
programs but has never built a structured way to understand
its customers beyond surface-level sales numbers.

This project answers the critical strategic question:

> "Is the business successfully building a loyal customer
> base, or is it reliant on continuous promotional activity?
> What strategic actions should be taken?"

---

## 📊 Key Results

| Metric | Finding |
|--------|---------|
| Total Customers | 3,900 |
| Total Revenue | $233,081 |
| Genuinely Loyal | 57% (2,223 customers) |
| Discount Dependent | 43% (1,677 customers) |
| Golden Market Cities | 1,013 customers |
| Retention Category | Accessories only |
| Ideal Customer | Female, PayPal, Clothing, Texas |

---

## 🔑 Key Business Findings

### Finding 1 — Loyalty Split
57% of customers are genuinely loyal and buy at full
price. 43% are discount dependent and only buy with
promotions. The brand has a healthy foundation but
risks growing discount dependency without intervention.

### Finding 2 — Promo Dependency
43% of purchases use discounts AND 43% use promo codes.
The same group uses both — the brand is training
customers to wait for promotions before buying.

### Finding 3 — Geographic Opportunity
1,013 customers live in Golden Market cities (high spend
+ low promo use). These are genuine brand advocates not
yet deliberately targeted by marketing.

### Finding 4 — Category Insight
Accessories is the ONLY retention category. Customers
who buy Accessories have 25.7 average previous purchases
vs 25.0 for other categories. Clothing is the entry
point — customers start with Clothing and move to
Accessories as they become loyal.

### Finding 5 — Ideal Customer Profile
- Gender: Female
- Payment: PayPal
- Category: Clothing (entry) + Accessories (retention)
- Frequency: Annual purchases
- Location: Texas

---

## 🏗️ Project Architecture
---
Raw Dataset (3,900 customers, 18 columns)

|

Data Cleaning (Python/Pandas)

- Handle missing values

- Fix data types

- Standardize text

|

Feature Engineering (Python)

- value_tier (Bronze/Silver/Gold/Platinum)

- promo_dependency_score (0.0/0.5/1.0)

- loyalty_type (Genuinely Loyal/Moderate/Discount Dependent)

- satisfaction_flag (High/Low)

- repeat_buyer_segment (Low/Medium/High)

- city_opportunity (Golden/Promo/Growth/Low)

- category_type (Entry/Retention)

|

SQL Analysis (MySQL)

- Q1: Loyal vs Discount customers

- Q2: Behavioral patterns

- Q3: Geographic analysis

- Q4: Promo restructuring

- Q5: Ideal customer profile

|

Power BI Dashboard (5 pages)

+ Retention Playbook (Word)

+ Executive Summary
---

## 📁 Project Structure
sql-retention-project/

|

|-- notebooks/

|   +-- sql_retention_project.ipynb   # Full Python code

|

|-- data/

|   |-- Dataset.csv                   # Original raw data

|   |-- cleaned_dataset.csv           # After cleaning

|   |-- customer_master_final.csv     # With all features

|   |-- powerbi_loyalty_summary.csv   # For Power BI Panel 1+2

|   |-- powerbi_geo_summary.csv       # For Power BI Panel 3

|   |-- powerbi_category_summary.csv  # For Power BI Panel 4

|   |-- powerbi_promo_summary.csv     # Promo sunset plan

|   +-- powerbi_icp_summary.csv       # Ideal customer profile

|

|-- dashboard/

|   +-- SQL_Retention_Dashboard.pbix  # Power BI file

|

|-- documents/

|   |-- Retention_Playbook.docx       # Full strategy doc

|   +-- Executive_Summary.pdf         # 1 page summary

|

+-- README.md


## 🔧 How To Run

### Step 1 - Install Dependencies
```bash
pip install pandas numpy sqlalchemy pymysql
pip install mysql-connector-python
```

### Step 2 - Run Python Analysis
```bash
jupyter notebook sql_retention_project.ipynb
```
Run all cells from top to bottom.

### Step 3 - Load MySQL Database
Update credentials in notebook:
```python
HOST     = "localhost"
USER     = "root"
PASSWORD = "your_password"
DATABASE = "sql_retention_db"
```

### Step 4 - Open Power BI Dashboard
Open SQL_Retention_Dashboard.pbix in Power BI Desktop

---

## 📊 Dashboard Pages

| Page | Content |
|------|---------|
| Executive Summary | KPIs + Key findings + ICP + Recommendations |
| Customer Pyramid | Value tier funnel + customer distribution |
| Promo Analysis | Loyalty vs discount + Promo sunset plan |
| Geographic Map | US city opportunity map + top cities |
| Category Funnel | Entry vs retention + category performance |

---

## 🎯 Business Recommendations

### 1. STOP Discounts (Month 1)
Target: Genuinely Loyal + Gold + Platinum (1,095 customers)
These customers already buy at full price.
Discounts are pure margin loss for this group.
Expected margin recovery: ~$14,689

### 2. LAUNCH Loyalty Program (Month 3)
Replace discounts with points-based rewards.
Points for: early access, free shipping, exclusive products.
Target: All 2,223 Genuinely Loyal customers.
Goal: 40% enrollment within 6 months.

### 3. TARGET Golden Market Cities (Month 2)
Increase marketing spend in Golden Market cities.
Focus: Female 45-55 on Instagram, Female 18-25 on TikTok.
These cities show genuine brand pull without discounts.

### 4. EXPAND Accessories (Month 3-4)
Upsell Accessories to Clothing buyers.
Accessories = only retention category.
Goal: 15% Clothing-to-Accessories conversion.

### 5. SPRING Acquisition Campaign
Female customers in Golden Market cities.
Focus on Clothing entry category.
No discounts — use urgency and free shipping.

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| Python 3.11 | Data cleaning + feature engineering |
| Pandas | Data manipulation |
| NumPy | Numerical calculations |
| MySQL | SQL queries + segmentation |
| SQLAlchemy | Python-MySQL connection |
| Power BI | Interactive dashboard |
| Jupyter Notebook | Analysis environment |

---

## 📈 Features Engineered

| Feature | Description | Business Use |
|---------|-------------|--------------|
| value_tier | Bronze/Silver/Gold/Platinum | Customer ranking |
| promo_dependency_score | 0.0/0.5/1.0 | Loyalty measurement |
| loyalty_type | 3 categories | Segment targeting |
| satisfaction_flag | High/Low | Churn risk |
| repeat_buyer_segment | Low/Medium/High | Loyalty depth |
| city_opportunity | 4 types | Geographic strategy |
| category_type | Entry/Retention | Product strategy |

---

## 💡 Analytical Challenge

The dataset has NO loyalty score, NO churn label,
and NO timestamps. Every concept was constructed
from available variables:

LOYALTY DEFINITION 1 (Used):
Based on promo_dependency_score
- 0.0 = Genuinely Loyal (no promos used)
- 0.5 = Moderate (one promo type)
- 1.0 = Discount Dependent (both promos)

LOYALTY DEFINITION 2 (Compared):
Based on repeat_buyer_segment
- Low: below 25th percentile of Previous Purchases
- Medium: 25th to 75th percentile
- High: above 75th percentile

Definition 1 was chosen because it directly
measures promotional behavior — more relevant
for the promo restructuring business objective.

---

## 👤 Author

Adarsh Kumar
- GitHub: https://github.com/Adarshk4212
- Project: SQL Customer Retention Strategy

---

## 📄 Dataset

Source: Customer Shopping Trends Dataset
Platform: Kaggle
Customers: 3,900
Features: 18 columns
Geography: United States

---

## 🏆 Project Outcome

This project demonstrates:
- Data-driven customer segmentation 
- SQL-based loyalty definition and measurement
- Business-ready Power BI dashboard
- Actionable retention strategy with clear tradeoffs
- Professional consulting-style deliverables
