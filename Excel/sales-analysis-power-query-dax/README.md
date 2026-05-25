# 📊 Sales Analysis Dashboard — Excel 360°

<div align="center">

### End-to-End Business Intelligence Solution in Microsoft Excel

Power Query • Data Model • DAX • Power Pivot • Interactive Dashboard

<br>

<img src="Screenshots/dashboard_overview.png" width="95%">

<br><br>

![Excel](https://img.shields.io/badge/Excel-Advanced-217346?style=for-the-badge\&logo=microsoftexcel\&logoColor=white)
![Power Query](https://img.shields.io/badge/Power_Query-ETL-blue?style=for-the-badge)
![DAX](https://img.shields.io/badge/DAX-Analytics-orange?style=for-the-badge)
![Power Pivot](https://img.shields.io/badge/Power_Pivot-Data_Model-yellow?style=for-the-badge)
![Project](https://img.shields.io/badge/Project-Completed-success?style=for-the-badge)

</div>

---

# 🎯 Project Objective

This project analyzes transactional sales data to uncover revenue trends, profitability patterns, product performance, and seasonal sales behaviour using Microsoft Excel.

The solution combines Power Query, Data Modelling, DAX, and interactive dashboards to deliver actionable business insights and KPI-driven reporting.

<table>
<tr>

<td width="50%">

## 📈 Analyze

* Revenue Trends
* Profit Growth
* Product Performance
* Seasonal Demand
* Sales Behaviour
* Profitability Patterns

</td>

<td width="50%">

## 💼 Deliver

* KPI Dashboards
* Interactive Reporting
* Business Insights
* Revenue Optimization
* Product Analysis
* Executive-Level Reporting

</td>

</tr>
</table>

---

# ❓ Business Questions Answered

* ✔ Which products generate the highest revenue?
* ✔ Which quarter drives maximum profitability?
* ✔ Are weekday sales stronger than weekends?
* ✔ Which products are underperforming?
* ✔ Which category contributes most to revenue?
* ✔ What seasonal patterns affect business growth?
* ✔ Which sales periods produce the best profit margin?
* ✔ How can inventory planning be optimized?

---

# 🔄 Analytics Pipeline

```text
📥 Raw CSV Data
        ↓
🧹 Power Query ETL
        ↓
🗂️ Data Cleaning & Transformation
        ↓
🧩 Excel Data Model
        ↓
🧮 DAX Calculations
        ↓
📊 Pivot Tables & Charts
        ↓
📈 Interactive Dashboard
        ↓
💡 Business Insights & Recommendations
```

---

# 🏗️ Technical Architecture

| Layer                  | Technology Used       |
| ---------------------- | --------------------- |
| 📂 Data Source         | CSV Transaction Data  |
| 🧹 ETL Layer           | Power Query           |
| 🧩 Data Modelling      | Excel Data Model      |
| 🧮 Calculation Layer   | DAX                   |
| 📊 Reporting Layer     | Pivot Tables          |
| 📈 Visualization Layer | Interactive Dashboard |

---

# 🛠️ Tools & Technologies

<table>
<tr>

<td align="center" width="20%">
<img src="https://img.icons8.com/color/96/microsoft-excel-2019.png" width="60"><br>
<b>Excel</b>
</td>

<td align="center" width="20%">
<img src="https://img.icons8.com/color/96/data-configuration.png" width="60"><br>
<b>Power Query</b>
</td>

<td align="center" width="20%">
<img src="https://img.icons8.com/color/96/combo-chart.png" width="60"><br>
<b>DAX</b>
</td>

<td align="center" width="20%">
<img src="https://img.icons8.com/color/96/database.png" width="60"><br>
<b>Data Model</b>
</td>

<td align="center" width="20%">
<img src="https://img.icons8.com/color/96/dashboard-layout.png" width="60"><br>
<b>Dashboard</b>
</td>

</tr>
</table>

---
## 🧩 KPI SNAPSHOT



<br>

| 🛒 Transactions | 📦 Order Quantity | 🏷️ Total Products | ✅ Sold Products |
| --------------- | ----------------- | ------------------ | --------------- |
| **109**         | **1,056**         | **606**            | **26**          |

<br>

| ❌ Unsold Products | 🏆 Best Sales Month | 🚲 Top Category | 📅 Strongest Quarter |
| ----------------- | ------------------- | --------------- | -------------------- |
| **580**           | **October**         | **Bikes**       | **Q4**               |

</div>




| 🛒 Transactions | 📦 Order Quantity | 🏷️ Total Products | ✅ Sold Products |
| --------------- | ----------------- | ------------------ | --------------- |
| **109**         | **1,056**         | **606**            | **26**          |


| ❌ Unsold Products | 🏆 Best Sales Month | 🚲 Top Category | 📅 Strongest Quarter |
| ----------------- | ------------------- | --------------- | -------------------- |
| **580**           | **October**         | **Bikes**       | **Q4**               |

---

# 🔵 Power Query — ETL Workflow

| Step                      | Description                             |
| ------------------------- | --------------------------------------- |
| 📥 Data Import            | Imported raw transactional CSV data     |
| 🧹 Data Cleaning          | Removed nulls & duplicates              |
| 🔤 Header Standardization | Renamed & formatted columns             |
| 📅 Date Table Creation    | Created custom calendar table           |
| 🏷️ Conditional Columns   | Added weekday/weekend logic             |
| 🔗 Query Merge            | Joined Product lookup table             |
| 📤 Load to Model          | Loaded transformed data into Data Model |

---

# 🧩 Data Model Structure

| Table   | Type            | Relationship |
| ------- | --------------- | ------------ |
| Sales   | Fact Table      | Many Side    |
| Product | Dimension Table | One-to-Many  |
| Date    | Dimension Table | One-to-Many  |

<br>

✅ Star Schema Architecture
✅ Optimized Pivot Performance
✅ Single-Direction Filtering
✅ Scalable Analytical Model

---

# 🧮 DAX Measures & KPI Logic

| KPI                   | DAX Logic                                 | Purpose                      |
| --------------------- | ----------------------------------------- | ---------------------------- |
| 💰 Total Revenue      | `SUM(Sales[Revenue])`                     | Total sales revenue          |
| 📈 Total Profit       | `SUM(Sales[Profit])`                      | Total profit generated       |
| 💵 Total COGS         | `SUM(Sales[CostOfGoodsSold])`             | Total operational cost       |
| 📦 Total Quantity     | `SUM(Sales[OrderQuantity])`               | Total units sold             |
| 🛒 Transactions       | `COUNTROWS(Sales)`                        | Transaction count            |
| 📊 Profit Margin %    | `DIVIDE([Total Profit], [Total Revenue])` | Profitability ratio          |
| 📅 YOY Revenue Growth | `SAMEPERIODLASTYEAR()`                    | Year-over-year comparison    |
| 🏷️ Weekday Profit %  | `CALCULATE()`                             | Weekday profitability        |
| 🚩 Revenue Flag       | `IF()` + `AVERAGEX()`                     | Above/below average analysis |

---

# 📊 Dashboard Analytics

| Analysis Area            | Metrics Used          |
| ------------------------ | --------------------- |
| 📈 Revenue Trends        | Revenue & Profit      |
| 📅 Monthly Analysis      | Transactions & Margin |
| 🏆 Quarterly Performance | Revenue Share         |
| 🚲 Product Analysis      | Revenue by Product    |
| 🗂️ Category Analysis    | Profit by Category    |
| 📆 Weekday vs Weekend    | Profit Contribution   |

---

# 🖼️ Dashboard Preview

<table>
<tr>

<td width="50%">
<img src="Screenshots/dashboard_overview.png">
</td>

<td width="50%">
<img src="Screenshots/power_query_steps.png">
</td>

</tr>

<tr>

<td width="50%">
<img src="Screenshots/data_model.png">
</td>

<td width="50%">
<img src="Screenshots/dax_measures.png">
</td>

</tr>
</table>

---

# 🔍 Key Insights

<table>
<tr>

<td width="50%">

## 🚲 Product Performance

* Bikes generated the majority of revenue
* High-margin bike products dominated sales
* Premium SKUs drove profitability

</td>

<td width="50%">

## 📆 Seasonal Trends

* October recorded highest sales activity
* Q4 generated strongest business performance
* Strong seasonal demand observed

</td>

</tr>

<tr>

<td width="50%">

## 💰 Profitability Analysis

* Achieved **42.6% profit margin**
* Generated **$874.6K total profit**
* Maintained healthy revenue-to-cost ratio

</td>

<td width="50%">

## 📦 Inventory Insights

* Only 26 products recorded sales
* 580 products remained unsold
* Opportunity exists for SKU optimization

</td>

</tr>
</table>

---

# 📊 Quarterly Profit Distribution

| Quarter | Profit Contribution |
| ------- | ------------------- |
| Q1      | 19.7%               |
| Q2      | 19.4%               |
| Q3      | 25.7%               |
| Q4      | 35.1%               |

---

# 📅 Weekday vs Weekend Performance

| Category      | Profit Share |
| ------------- | ------------ |
| Weekday Sales | 74.9%        |
| Weekend Sales | 25.1%        |

---

# 💼 Business Recommendations

| Recommendation                               | Expected Impact           |
| -------------------------------------------- | ------------------------- |
| 🚲 Prioritize top-performing Bike SKUs       | Improve profitability     |
| 📈 Increase Q3 marketing campaigns           | Reduce seasonal gap       |
| 📦 Review unsold inventory                   | Reduce carrying costs     |
| 🎯 Improve low-performing product visibility | Increase product movement |
| 📊 Expand dashboard automation               | Faster business reporting |

---

# 🔍 Transformation Overview

| Before               | After                 |
| -------------------- | --------------------- |
| Raw CSV data         | Interactive dashboard |
| Manual analysis      | Automated reporting   |
| Unstructured dataset | Star Schema model     |
| No KPI visibility    | Business insights     |
| Static reports       | Dynamic filtering     |

---

# 🧠 Skills Demonstrated

<table>
<tr>

<td width="33%" valign="top">

## 📊 Analytics Skills

* Power Query ETL
* Data Cleaning
* Data Transformation
* Revenue Analysis
* Profitability Analysis
* Inventory Analysis
* Time Intelligence

</td>

<td width="33%" valign="top">

## 🧩 Technical Skills

* Excel Data Modelling
* Star Schema Design
* DAX Calculations
* Power Pivot
* Pivot Table Analytics
* Interactive Reporting
* Dashboard Automation

</td>

<td width="33%" valign="top">

## 📈 Business Intelligence

* KPI Development
* Business Reporting
* Dashboard Design
* Data Visualization
* Insight Generation
* Analytical Storytelling
* Executive Reporting

</td>

</tr>
</table>

---

# 📂 Repository Structure

```bash
sales-analysis-power-query-dax/
│
├── 📁 Data/
├── 📁 Screenshots/
├── 📁 Docs/
├── 📄 sales_analysis.xlsm
├── 📄 README.md
└── 📄 .gitignore
```

---

# 🚀 How to Use

| Step | Action                         |
| ---- | ------------------------------ |
| 1️⃣  | Download `sales_analysis.xlsm` |
| 2️⃣  | Enable Macros                  |
| 3️⃣  | Open Dashboard Sheets          |
| 4️⃣  | Use slicers for filtering      |
| 5️⃣  | Explore Power Pivot Model      |

---

# 👩‍💻 Author

<div align="center">

## Jennisha K

### Data Analyst | Excel • SQL • Power BI • Tableau • Python

📧 [jennisha97@gmail.com](mailto:jennisha97@gmail.com)

🔗 [www.linkedin.com/in/jennisha-k-66a195191](http://www.linkedin.com/in/jennisha-k-66a195191)

</div>

---

<div align="center">

# ⭐ If You Found This Project Useful, Star The Repository

### 📊 Turning Raw Data into Business Insights

</div>

