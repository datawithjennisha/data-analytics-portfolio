# 📊 HR Analytics Dashboard — Workforce Attrition & People Intelligence

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)
![Excel](https://img.shields.io/badge/Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![Power Query](https://img.shields.io/badge/Power%20Query-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)
![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=for-the-badge)
![Domain](https://img.shields.io/badge/Domain-HR%20Analytics-blueviolet?style=for-the-badge)

> **An interactive HR Analytics Dashboard built in Microsoft Power BI that transforms raw employee data into actionable workforce intelligence — enabling HR leaders to identify attrition drivers, analyze department-wise risk, and make data-driven retention decisions.**

---

## 📋 Table of Contents

- [Project Overview](#project-overview)
- [Live Dashboard Preview](#live-dashboard-preview)
- [Business Problem](#business-problem)
- [Objectives](#objectives)
- [KPIs & Metrics](#kpis--metrics)
- [Dashboard Insights](#dashboard-insights)
- [Tools & Technologies](#tools--technologies)
- [Folder Structure](#folder-structure)
- [Setup & Installation](#setup--installation)
- [DAX Measures](#dax-measures)
- [Data Cleaning Steps](#data-cleaning-steps)
- [Business Recommendations](#business-recommendations)
- [Future Enhancements](#future-enhancements)
- [Key Learnings](#key-learnings)
- [Connect](#connect)

---

## 🎯 Project Overview

This end-to-end HR Analytics Dashboard was built in Microsoft Power BI to give HR departments and business leaders a 360-degree view of workforce health. The dashboard integrates employee demographic, compensation, department, and satisfaction data to surface attrition patterns that are invisible in traditional spreadsheet-based reporting.

| Attribute | Details |
|---|---|
| Tool | Microsoft Power BI Desktop |
| Domain | Human Resources / People Analytics |
| Total Employees Analyzed | 588 |
| Active Employees | 477 |
| Attrition Count | 111 |
| Overall Attrition Rate | 18.9% |
| Average Employee Age | 30.98 years |
| Average Experience | 5.95 years |
| Dashboard Pages | Multi-page with Age Group Filter |
| Visuals Used | Donut chart, bar chart, matrix table, KPI cards, trend line |

---

## 📸 Live Dashboard Preview

<div align="center">

<img src="Screenshot/dashboard_overview.png" width="100%"/>

</div>

> *Dashboard showing KPI cards, attrition by department, salary slab, job role & satisfaction matrix, age group distribution, gender split, and experience trend — all filterable by age group (18-25, 26-35, 36-45, 46-55, 55+)*

---

## 🏢 Business Problem

The organization employs **588 staff** and is experiencing an attrition rate of **18.9%** — nearly double the industry benchmark of 10%. HR leadership lacked a unified, interactive view of workforce data to understand:

- **Which departments** are losing the most employees
- **Which salary bands** are highest attrition risk
- **Which job roles** have the lowest satisfaction scores
- **What age and experience cohorts** are most vulnerable to exit
- **How gender distribution** maps to attrition patterns

Without this visibility, retention interventions were reactive and poorly targeted.

---

## 🎯 Objectives

1. Build a filterable, multi-view HR dashboard in Power BI with age-group segmentation
2. Quantify attrition across departments, salary slabs, job roles, and gender
3. Cross-reference job satisfaction scores (1–4 scale) with attrition counts by role
4. Identify high-risk employee cohorts using demographic and compensation data
5. Surface actionable retention recommendations for HR leadership

---

## 📈 KPIs & Metrics

| KPI | Value | Status |
|---|---|---|
| Total Employees | 588 | — |
| Active Employees | 477 | — |
| Attrition Count | 111 | — |
| Attrition Rate | 18.9% | 🔴 Above 10% benchmark |
| Average Age | 30.98 years | — |
| Average Experience | 5.95 years | — |
| Finance Dept Attrition | 55% of dept | 🔴 Critical |
| HR Dept Attrition | 30% of dept | 🟡 High |
| Administration Dept Attrition | 5% of dept | 🟢 Low |
| Highest Attrition Salary Band | 6–10 LPA (157 exits) | 🔴 Priority |
| Sales Rep Attrition | 12 employees | 🔴 Highest by role |

---

## 📊 Dashboard Insights

### 1. Department-Wise Attrition
Finance leads attrition at **55% (61 employees)**, followed by Human Resources at **30% (33 employees)**. Administration shows the lowest attrition at just **5% (3 employees)**. This concentration in Finance and HR signals systemic issues in these functions — likely linked to workload, compensation, or growth opportunities.

### 2. Attrition by Salary Slab
The **6–10 LPA band** records the highest attrition with **157 exits**, followed by the 0–3 LPA band at **114** and 3–6 LPA at **117**. Employees earning **10+ LPA** have the lowest attrition at **89**, confirming that compensation is a primary retention driver. Over 85% of all exits occur below the 10 LPA threshold.

### 3. Attrition by Job Role & Satisfaction Matrix
The satisfaction matrix reveals:
- **Sales Representatives**: 12 exits — highest by single role
- **Sales Executives**: 27 exits with satisfaction scores spread across 1–4
- **Laboratory Technicians**: 29 exits — second highest overall
- **Research Scientists**: 28 exits
- Roles with satisfaction score of **1 (Very Dissatisfied)** show disproportionately high attrition across all job types

### 4. Age Group Distribution
The **26–35 age band** dominates the workforce with **588 employees** in this cohort (when filtered). This is the organization's most productive age segment and also its highest attrition risk group — requiring targeted engagement and growth path interventions.

### 5. Attrition by Gender
The gender split shows approximately **60% Male** and **40% Female** attrition contributors, indicating attrition is not gender-isolated but reflects a broader organizational pattern.

### 6. Attrition Trend by Experience
The experience-trend line shows attrition spikes at the **0–5 year mark**, peaking around the **2–3 year experience point** (spike visible at value 12 on the trend chart). This is the classic "mid-junior exit window" — employees who have gained enough skills to be marketable but have not yet received enough growth investment to stay.

---

## 🛠 Tools & Technologies

| Tool | Purpose |
|---|---|
| Microsoft Power BI Desktop | Dashboard development, DAX measures, data modelling |
| Power Query (M Language) | Data ingestion, transformation, cleaning |
| DAX (Data Analysis Expressions) | KPI calculations, conditional measures, matrix logic |
| Microsoft Excel (.xlsx) | Source dataset |
| Star Schema Modelling | Fact-dimension table relationships in Power BI model view |
| GitHub | Version control and portfolio hosting |

4. If a data source path error appears:
   - Click **Transform Data** → **Data Source Settings**
   - Update the file path to your local `dataset/raw/` folder

5. Click **Refresh** in Power BI Desktop to reload all visuals

6. Use the **Age Group buttons** (18-25, 26-35, 36-45, 46-55, 55+) to filter the entire dashboard

---

## 📐 DAX Measures

| Measure Name | DAX Formula | Purpose |
|---|---|---|
| **Attrition Rate** | `DIVIDE(COUNTROWS(FILTER('HR_Data', 'HR_Data'[Attrition] = "Yes")), COUNTROWS('HR_Data'), 0) * 100` | Calculates overall employee attrition percentage |
| **Active Employees** | `COUNTROWS(FILTER('HR_Data', 'HR_Data'[Attrition] = "No"))` | Counts currently active employees |
| **Attrition Count** | `COUNTROWS(FILTER('HR_Data', 'HR_Data'[Attrition] = "Yes"))` | Counts employees who left the organization |
| **Average Age** | `AVERAGE('HR_Data'[Age])` | Calculates average employee age |
| **Average Experience** | `AVERAGE('HR_Data'[YearsAtCompany])` | Measures average employee experience |
| **Department Attrition %** | `DIVIDE(CALCULATE([Attrition Count], ALLEXCEPT('HR_Data', 'HR_Data'[Department])), CALCULATE(COUNTROWS('HR_Data'), ALLEXCEPT('HR_Data', 'HR_Data'[Department])), 0) * 100` | Calculates attrition percentage by department |
| **Avg Satisfaction by Role** | `CALCULATE(AVERAGE('HR_Data'[JobSatisfaction]), ALLEXCEPT('HR_Data', 'HR_Data'[JobRole]))` | Calculates average job satisfaction score by role |

## 🧹 Data Cleaning Steps

| # | Step | What Was Done |
|---|---|---|
| 01 | Promoted Headers | Set first row as column names |
| 02 | Data Type Enforcement | Age, Salary, Experience → Numeric |
| 03 | Attrition Flag | Converted Yes/No → 1/0 for aggregation |
| 04 | Removed Redundant Columns | Dropped EmployeeCount, StandardHours, Over18 |
| 05 | Age Band Column | Created groupings: 18-25, 26-35, 36-45, 46-55, 55+ |
| 06 | Salary Slab Column | Grouped MonthlyIncome into LPA bands: 0-3, 3-6, 6-10, 10+ |
| 07 | Null Validation | Confirmed 0 null values across all columns |
| 08 | Department Standardization | Ensured consistent naming across department field |

---

## 💡 Business Recommendations

| Priority | Insight | Recommendation | Expected Impact |
|---|---|---|---|
| 🔴 Critical | Finance dept: 55% attrition | Immediate compensation review + 1:1 retention conversations for Finance team | Reduce Finance exits by 30% |
| 🔴 Critical | 6–10 LPA band: highest exits | Market salary benchmarking; bring mid-band salaries to 75th percentile | Reduce mid-band attrition by 25% |
| 🔴 High | Sales Representatives: 12 exits | Introduce performance bonuses, clear promotion path, weekly coaching | Reduce Sales Rep attrition by 35% |
| 🟡 High | Experience spike at 2–3 years | Launch "Year 2 Engagement Programme" — mentoring, skill development, internal mobility | Retain 40% of at-risk junior staff |
| 🟡 Medium | Satisfaction score 1 → high attrition | Quarterly pulse surveys; auto-flag any score ≤ 2 for manager action | Reduce dissatisfaction-driven exits |
| 🟢 Monitor | 26–35 age band dominates workforce | Invest in leadership development and fast-track programmes for this cohort | Long-term retention of core workforce |

---

## 🚀 Future Enhancements

- [ ] **Predictive Attrition Model** — Integrate Python/Azure ML to assign flight-risk scores per employee
- [ ] **Time Intelligence** — Add month-over-month attrition trend using DAX SAMEPERIODLASTYEAR
- [ ] **Row-Level Security (RLS)** — Restrict department-level data access per HR Business Partner
- [ ] **Live Data Connection** — Replace Excel source with SharePoint Online or Azure SQL
- [ ] **Mobile Layout** — Design Power BI mobile view for on-the-go HR manager access
- [ ] **What-If Salary Scenario** — Model projected attrition impact of 5%/10%/15% salary increments

---

## 📚 Key Learnings

- DAX filter context vs. row context is foundational — `CALCULATE()` was the most critical function in this project
- Visual design communicates faster than data tables — chart type selection directly affects decision speed
- The satisfaction matrix (job role × score) was the most complex visual to build but delivered the richest insight
- Age group buttons (bookmark-based filtering) significantly improved dashboard usability for non-technical HR users
- Star schema modelling reduced DAX complexity compared to a flat table approach

---

## 🤝 Connect with Me

**Jennisha K** | Data Analyst | Chennai, Tamil Nadu

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/jennisha-k-66a195191)
[![Email](https://img.shields.io/badge/Email-D14836?style=flat&logo=gmail&logoColor=white)](mailto:jennisha97@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=flat&logo=github&logoColor=white)](https://github.com/jennisha97-maker)

---

> *"Turning Data into Decisions"*

⭐ If this project helped you, please consider starring the repository!
[![GitHub](https://img.shields.io/badge/GitHub...)](https://github.com/jennisha97-maker)
