# 📊 Sales Segmentation – RFM Analysis | Power BI Dashboard

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)
![Excel](https://img.shields.io/badge/Excel-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)

> **Segmenting 789 customers using RFM (Recency, Frequency, Monetary) methodology to uncover Champions, At-Risk, Lost, and other behavioral segments from 8,511 retail transactions.**

---

## 📸 Dashboard Preview

![Sales RFM Dashboard](Sales_RFM_dashboard.png)

---

## 🧠 Project Overview

This Power BI project applies **RFM-based customer segmentation** on the Superstore 2025 dataset — 8,511 rows of US retail transactions across Furniture, Office Supplies, and Technology categories — spanning the year 2024.

RFM analysis answers three business-critical questions:

| Dimension | Question | How It's Measured |
|---|---|---|
| 🕐 **Recency** | How recently did the customer buy? | Days since last order vs. max order date |
| 🔁 **Frequency** | How often do they buy? | Distinct order count per customer |
| 💰 **Monetary** | How much do they spend? | Total sales value per customer |

Each customer is scored 1–5 on all three dimensions and assigned to a **business segment** — enabling data-driven targeting and retention strategies.

---

## 📌 Dataset Overview

| Field | Detail |
|---|---|
| Source | Superstore 2025 (US Retail) |
| Total Rows | 8,511 transactions |
| Unique Customers | 789 |
| Unique Orders | 4,251 |
| Total Sales | ₹ 19,65,639 (~₹ 2M) |
| Categories | Furniture, Office Supplies, Technology |
| Customer Segments | Consumer, Corporate, Home Office |
| Regions | East, West, Central, South |
| Sub-Categories | 17 |
| Date Range | 2024 (Jan–Dec) |

**Columns in dataset:**
`Row ID` · `Order ID` · `Order Date` · `Ship Mode` · `Customer ID` · `Customer Name` · `Segment` · `Country/Region` · `City` · `State` · `Postal Code` · `Region` · `Product ID` · `Category` · `Sub-Category` · `Product Name` · `Sales` · `Quantity` · `Discount` · `Profit`

---

## 📊 Dashboard KPIs

| Metric | Value |
|---|---|
| 💰 Total Sales | ₹ 2M |
| 📅 Avg Recency | 200 days |
| 🔁 Avg Frequency | 5 orders |
| 💵 Avg Monetary | ₹ 2.49K |

---

## 👥 RFM Customer Segments

| Segment | Count | Description |
|---|---|---|
| 🏆 Champions | 202 | Bought recently, buy often, spend the most |
| ⚠️ At Risk | 98 | Were good customers — haven't purchased recently |
| 💎 Loyal Customers | 65 | Frequent buyers with consistent engagement |
| 💸 Big Spenders | 86 | High monetary value, lower recency |
| 📉 Lost | 44 | Lowest RFM scores across all 3 dimensions |
| 🔵 Others | 294 | Mixed patterns, not fitting above categories |

---

## 🗂️ Data Model

| Table | Type | Purpose |
|---|---|---|
| `Superstore 2025` | Fact | Raw transactional data (8,511 rows) |
| `RFM_Calculation` | Calculated Table | Aggregated RFM scores per customer |
| `DateTable` | Dimension | Calendar table for time intelligence |
| `Tbl_Measure` | Measure Table | All DAX KPI measures |

--

## 🎯 Business Problem

Retail businesses often have thousands of customers, but not all customers contribute equally to revenue. Applying the same marketing strategy to every customer increases costs and reduces campaign effectiveness.

The challenge is to identify:

* Which customers generate the most value?
* Which customers are likely to stop purchasing?
* Which customers should receive retention offers?
* How can marketing campaigns be personalized for better ROI?

---

## 🎯 Project Objective

The primary objective of this analysis is to leverage RFM methodology to:

* Retain high-value customers
* Reduce customer churn
* Improve marketing ROI
* Increase repeat purchases
* Personalize customer engagement strategies
* Support data-driven business decisions

---

## 📖 What is RFM Analysis?

RFM is a customer segmentation technique that evaluates customers based on three key metrics:

| Metric    | Description                  | Business Question                       |
| --------- | ---------------------------- | --------------------------------------- |
| Recency   | Days since the last purchase | How recently did the customer buy?      |
| Frequency | Number of purchases          | How often does the customer buy?        |
| Monetary  | Total amount spent           | How much money does the customer spend? |

Customers are scored and grouped into meaningful business segments based on these metrics.

---

## 🛠 Tools & Technologies

* Power BI
* DAX
* Power Query
* Excel
* Data Modeling
* Data Visualization

---

## 📈 Dashboard KPIs

| KPI                    | Value       |
| ---------------------- | ----------- |
| Total Sales            | ₹2M         |
| Average Recency        | 200 Days    |
| Average Frequency      | 5 Purchases |
| Average Monetary Value | ₹2.49K      |

---

## 🔍 Key Insights

### 1. Customer Segmentation Analysis

Customers were categorized into behavioral segments:

| Segment         | Insight                                 | Recommended Action               |
| --------------- | --------------------------------------- | -------------------------------- |
| Champions       | Recent, frequent, high-value customers  | Reward with loyalty programs     |
| Loyal Customers | Consistent purchasers                   | Upsell and cross-sell products   |
| Big Spenders    | Major revenue contributors              | Provide premium offers           |
| At Risk         | Previously active but becoming inactive | Launch retention campaigns       |
| Lost Customers  | Long period without purchases           | Run win-back campaigns           |
| Others          | Average customer behavior               | Nurture with targeted promotions |

---

### 2. Sales Trend Analysis

#### Findings

* Monthly sales fluctuate throughout the year.
* Peak months indicate seasonal demand patterns.
* Certain months show reduced sales activity.

#### Business Impact

* Supports inventory planning.
* Improves workforce allocation.
* Enables better forecasting and budgeting.

---

### 3. Revenue Concentration

#### Findings

A relatively small group of customers, particularly Champions and Big Spenders, contributes a significant portion of total revenue.

#### Business Impact

* Retaining these customers protects revenue streams.
* Customer retention efforts can be prioritized for maximum impact.

---

### 4. Customer Retention Risk

#### Findings

A considerable number of customers belong to the At Risk and Lost segments.

#### Business Impact

* Early intervention can prevent churn.
* Targeted campaigns can improve customer lifetime value (CLV).

---

### 5. Customer Purchase Behavior

#### Findings

* Customers purchase approximately 5 times on average.
* Average spending per customer is around ₹2.49K.
* Average recency of 200 days indicates that many customers have not purchased recently.

#### Business Impact

* Highlights opportunities for re-engagement campaigns.
* Helps identify inactive customer groups.

---

## 💡 Business Recommendations

### 🏆 Champions

* VIP membership programs
* Exclusive discounts
* Early access to new products

### 🤝 Loyal Customers

* Cross-selling opportunities
* Referral reward programs
* Loyalty incentives

### 💰 Big Spenders

* Premium product recommendations
* Personalized promotions
* Priority customer support

### ⚠️ At Risk Customers

* Reminder emails
* Limited-time discounts
* Personalized engagement campaigns

### ❌ Lost Customers

* Win-back campaigns
* Reactivation offers
* Special promotional discounts

---

## 📊 Business Value Delivered

This dashboard enables stakeholders to:

* Identify high-value customers
* Improve customer retention strategies
* Reduce churn risk
* Optimize marketing spend
* Increase customer lifetime value
* Make data-driven business decisions


## 🚀 Skills Demonstrated

* Customer Segmentation
* Business Intelligence
* Data Analysis
* Data Visualization
* Power BI Dashboard Development
* DAX Calculations
* KPI Design
* Retail Analytics
* Customer Retention Analysis
* Stakeholder Reporting



## 📊 Visuals in the Dashboard

- **KPI Cards** — Total Sales, Avg Recency, Avg Frequency, Avg Monetary (with YoY color indicators)
- **Total Sales Trend by Month** — Combo chart: bar (Total Sales) + line (Total Customers)
- **Count of Customers by Segment** — Horizontal bar chart
- **Count of Customer by Segment (Category)** — Donut chart split by Furniture / Office Supplies / Technology
- **Customer RFM Detail Table** — Customer ID, Name, Segment, Recency, Frequency, Monetary

---

## 🔍 Business Insights

- **Champions (202 customers)** are the highest value group — reward with loyalty programs and early-access offers.
- **At Risk (98 customers)** were once active but show declining engagement — win-back campaigns with personalized offers recommended.
- **Lost (44 customers)** scored lowest across all 3 RFM dimensions — analyze exit patterns to prevent future churn.
- **Big Spenders (86 customers)** have high monetary value but lower recency — re-engagement emails can revive them.
- **Technology** drives the highest per-order value; **Office Supplies** generates high frequency but lower average ticket size.
- Seasonal spike observed in **November–December**, indicating strong year-end buying behaviour.

---

## 🗃️ Repository Structure

```
📁 Sales-RFM-Analysis-PowerBI/
│
├── 📄 README.md
├── 📊 Sales_RFM.pbix
├── 📁 assets/
│   └── Sales_RFM_Dashboard.png
├── 📁 data/
│   └── Superstore_2025.csv
└── 📁 dax/
    └── DAX_Used.docx
```

---

## 🛠️ Tools & Technologies

| Tool | Usage |
|---|---|
| Power BI Desktop | Dashboard design, RFM visualisation |
| DAX | Measures, calculated tables, scoring logic, YoY analysis |
| Power Query (M) | Data transformation & cleaning |
| Excel / CSV | Source data — Superstore_2025 |

---

## 🚀 How to Use

1. Clone or download this repository
2. Open `Sales_RFM.pbix` in **Power BI Desktop**
3. Update the data source path to your local `Superstore_2025.csv` if prompted
4. Refresh the dataset — all RFM scores and segments auto-calculate via DAX
5. Explore all 3 report pages: `Sales_RFM`, `Page1`, `Duplicate of Sales_RFM`

---

## 👩‍💻 About Me

**Jennisha K** | Data Analyst | Chennai, India

Skilled in Power BI · SQL · Tableau · Excel · Python
Domain: Banking, Financial Services & Retail Analytics
Actively seeking Data Analyst / MIS Analyst / Power BI Developer roles

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat&logo=linkedin)](https://linkedin.com/in/your-profile)
[![GitHub](https://img.shields.io/badge/GitHub-Portfolio-181717?style=flat&logo=github)](https://github.com/your-username)

---

*⭐ If this project helped you, give it a star!*
