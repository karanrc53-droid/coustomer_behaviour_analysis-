# 🛍️ Customer Shopping Behavior Analysis

**Author:** Karan Yadav  
**Tools Used:** Python · PostgreSQL · Power BI  
**Dataset Size:** 3,900 rows · 18 columns

---

## 📌 Project Overview

This end-to-end data analytics project analyzes customer shopping behavior using transactional retail data. The goal is to uncover actionable insights into spending patterns, customer segments, product preferences, and subscription behavior to guide strategic business decisions.

> **Business Question:** *"How can the company leverage consumer shopping data to identify trends, improve customer engagement, and optimize marketing and product strategies?"*

---

## 📁 Repository Structure

```
customer-shopping-behavior-analysis/
│
├── customer_shopping_behavior.csv          # Raw dataset
├── Customer_Shopping_Behavior_Analysis.ipynb  # Python EDA & data cleaning
├── customer_behavior_sql_queries.sql       # 10 SQL business queries
├── customer_behavior_dashboard.pbix        # Power BI interactive dashboard
├── Customer_Shopping_Behavior_Analysis.pdf # Full project report
├── Customer-Shopping-Behavior-Analysis.pptx  # Stakeholder presentation
├── Business_Problem_Document.pdf           # Problem statement
└── README.md
```

---

## 📊 Dataset Summary

| Feature | Details |
|---|---|
| Rows | 3,900 |
| Columns | 18 |
| Missing Data | 37 values in `Review Rating` |

**Key columns:** Customer ID, Age, Gender, Location, Item Purchased, Category, Purchase Amount (USD), Season, Review Rating, Subscription Status, Shipping Type, Discount Applied, Previous Purchases, Frequency of Purchases

---

## 🐍 Python – EDA & Data Preparation

Performed in `Customer_Shopping_Behavior_Analysis.ipynb`:

- **Data Loading & Exploration** – `df.info()`, `.describe()`, null checks
- **Missing Data Handling** – Imputed `Review Rating` using median per product category
- **Column Standardization** – Renamed all columns to snake_case
- **Feature Engineering** – Created `age_group` (binned) and `purchase_frequency_days`
- **Data Consistency Check** – Verified `discount_applied` and `promo_code_used` were redundant; dropped `promo_code_used`
- **Database Integration** – Loaded cleaned DataFrame into PostgreSQL for SQL analysis

---

## 🗄️ SQL – Business Transaction Analysis

10 structured queries written in PostgreSQL (`customer_behavior_sql_queries.sql`):

| # | Question |
|---|---|
| Q1 | Revenue by gender |
| Q2 | High-spending discount users (above-average spend with discount) |
| Q3 | Top 5 products by average review rating |
| Q4 | Standard vs. Express shipping — average purchase comparison |
| Q5 | Subscribers vs. non-subscribers — avg spend & total revenue |
| Q6 | Top 5 discount-dependent products |
| Q7 | Customer segmentation: New / Returning / Loyal (CTE) |
| Q8 | Top 3 products per category (Window Function – ROW_NUMBER) |
| Q9 | Repeat buyers (>5 purchases) vs. subscription likelihood |
| Q10 | Revenue contribution by age group |

**Concepts used:** Subqueries, CTEs, Window Functions, CASE WHEN, GROUP BY, ROUND, aggregations

---

## 📈 Key Findings

- **Male customers** generated ~2x revenue ($157,890) vs. female ($75,191)
- **839 customers** used discounts but still spent above average — high-value discount users
- **Gloves** had the highest average review rating (3.86); top 5 were all accessories/footwear
- **Express shipping** users spent slightly more ($60.48) than Standard ($58.46)
- **Subscribers** had similar avg spend ($59.49) to non-subscribers ($59.87) — low differentiation
- **80% of customers** are in the Loyal segment (3,116 of 3,900)
- **Young Adults** were the top revenue-generating age group ($62,143)

---

## 📊 Power BI Dashboard

The interactive dashboard (`customer_behavior_dashboard.pbix`) includes:

- KPI cards: Total customers, Average Purchase Amount, Average Review Rating
- % of customers by subscription status (donut chart)
- Revenue & Sales by Category and Age Group
- Slicers: Gender, Category, Subscription Status, Shipping Type

---

## 💡 Business Recommendations

1. **Boost Subscriptions** – Current subscribers show no spending premium; introduce exclusive perks to drive value
2. **Loyalty Programs** – 83 new customers need onboarding campaigns to retain them
3. **Review Discount Policy** – ~50% of Hat/Sneaker purchases use discounts — review margin impact
4. **Product Positioning** – Promote Gloves, Sandals, Boots (top-rated) in campaigns
5. **Targeted Marketing** – Focus on Young Adults and Express shipping users for high-ROI campaigns

---

## ⚙️ How to Run

1. **Python Notebook** – Open `Customer_Shopping_Behavior_Analysis.ipynb` in Jupyter. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn sqlalchemy psycopg2
   ```
2. **SQL Queries** – Run `customer_behavior_sql_queries.sql` in any PostgreSQL client (e.g., pgAdmin, DBeaver) after loading the dataset
3. **Power BI Dashboard** – Open `customer_behavior_dashboard.pbix` in Power BI Desktop (free download from Microsoft)

---

## 🔗 Connect

**LinkedIn:** [linkedin.com/in/karanyadav] *([update with your actual URL](https://www.linkedin.com/in/karan12yadav/))*  
**Email:** *(karanrc53@gmail.com)*

