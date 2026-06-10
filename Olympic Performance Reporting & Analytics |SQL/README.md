# 🏅 Olympic Performance Analytics Dashboard

> A SQL & Power BI analytics project focused on Olympic athlete performance, participation trends, medal efficiency, and economic impact analysis through interactive reporting and business intelligence dashboards.

---

## 📌 Project Overview

The Olympic Performance Analytics Dashboard transforms Olympic data into meaningful business insights using SQL reporting and Power BI visualization techniques.

The project integrates athlete information, Olympic event results, country demographics, and economic indicators to analyze performance trends, participation patterns, medal efficiency, and regional success factors.

Through advanced SQL queries and interactive Power BI dashboards, the project demonstrates how data can be leveraged to support analytical reporting, KPI tracking, benchmarking, and decision-making.

---

## 🎯 Business Objectives

- Identify top-performing Olympic athletes based on gold medal achievements.
- Analyze participation trends across Olympic events by gender.
- Measure country-level medal efficiency using population-adjusted metrics.
- Assess the relationship between GDP and Olympic performance.
- Build an interactive Power BI dashboard for performance monitoring and analysis.

---

## 🗄️ Database Schema

The project uses a relational database consisting of five tables:

### Athletes
Stores athlete demographic information.

### Summer Games
Stores Summer Olympic event participation and medal results.

### Winter Games
Stores Winter Olympic event participation and medal results.

### Countries
Stores country and regional information.

### Country Statistics
Stores GDP, population, and Nobel Prize data by country.

---

## 🛠️ Tools & Technologies

| Category | Technology |
|-----------|------------|
| Database | SQL |
| Reporting | SQL Queries |
| Visualization | Power BI |
| Data Modeling | Relational Database |
| Analytics | KPI Reporting |
| Dashboarding | Power BI Desktop |

---

## 📊 Dashboard KPIs

### Total Athletes

Tracks the total number of athletes participating in Olympic events.

### Total Medals

Measures total medals earned across all events.

### Countries Analyzed

Tracks the number of participating countries.

### Total Gold Medals

Measures overall gold medal achievements.

---

# 📈 Analytical Reports

---

## 01. Top Athletes by Gold Medals

### Objective

Identify the most successful Olympic athletes based on total Summer Olympic gold medals.

### SQL Query

```sql
WITH athlete_gold_medals AS (
    SELECT
        a.id,
        a.name,
        SUM(sg.gold) AS total_gold_medals
    FROM summer_games sg
    JOIN athletes a
        ON sg.athlete_id = a.id
    GROUP BY
        a.id,
        a.name
)

SELECT
    name,
    total_gold_medals,
    RANK() OVER (
        ORDER BY total_gold_medals DESC
    ) AS athlete_rank
FROM athlete_gold_medals
ORDER BY athlete_rank;
```

### Skills Used

- CTEs
- Joins
- Aggregate Functions
- Window Functions
- Ranking Functions

### Power BI Visual

- Horizontal Bar Chart

---

## 02. Gender Participation by Event

### Objective

Analyze athlete participation patterns across Olympic events by gender.

### SQL Query

```sql
SELECT
    sg.event,
    a.gender,
    COUNT(DISTINCT sg.athlete_id) AS participant_count
FROM summer_games sg
JOIN athletes a
    ON sg.athlete_id = a.id
GROUP BY
    sg.event,
    a.gender
ORDER BY
    sg.event,
    participant_count DESC;
```

### Skills Used

- Joins
- GROUP BY
- COUNT(DISTINCT)
- Demographic Analysis

### Power BI Visual

- 100% Stacked Column Chart

---

## 03. Country Medal Efficiency Analysis

### Objective

Measure Olympic performance relative to country population.

### SQL Query

```sql
WITH country_medals AS (
    SELECT
        country_id,
        SUM(gold + silver + bronze) AS total_medals
    FROM summer_games
    GROUP BY country_id
)

SELECT
    c.country,
    cm.total_medals,
    cs.pop_in_millions,
    ROUND(
        cm.total_medals / cs.pop_in_millions,
        2
    ) AS medals_per_million
FROM country_medals cm
JOIN countries c
    ON cm.country_id = c.id
JOIN country_stats cs
    ON cm.country_id = cs.country_id
WHERE cs.year = 2024
ORDER BY medals_per_million DESC;
```

### Skills Used

- KPI Reporting
- CTEs
- Joins
- Aggregate Functions
- Analytical Reporting

### Power BI Visual

- Clustered Column Chart

---

## 04. GDP vs Olympic Performance Analysis

### Objective

Evaluate the relationship between economic strength and Olympic success.

### SQL Query

```sql
WITH country_performance AS (
    SELECT
        country_id,
        SUM(gold + silver + bronze) AS total_medals
    FROM summer_games
    GROUP BY country_id
)

SELECT
    c.region,
    ROUND(AVG(cs.gdp), 2) AS avg_regional_gdp,
    SUM(cp.total_medals) AS total_medals,
    ROUND(
        AVG(cp.total_medals),
        2
    ) AS avg_medals_per_country
FROM country_performance cp
JOIN countries c
    ON cp.country_id = c.id
JOIN country_stats cs
    ON cp.country_id = cs.country_id
WHERE cs.year = 2024
GROUP BY c.region
ORDER BY total_medals DESC;
```

### Skills Used

- CTEs
- Joins
- Aggregate Functions
- Comparative Analysis
- Business Intelligence Reporting

### Power BI Visual

- Scatter Plot

---

## 🔍 Key Insights

### Athlete Performance

- Identified the highest-performing Olympic athletes based on gold medal achievements.
- Generated athlete ranking reports using SQL Window Functions.
- Revealed concentration of medal success among elite athletes.

### Gender Participation

- Evaluated participation patterns across Olympic events.
- Highlighted differences in gender representation across sports.
- Provided demographic participation insights.

### Medal Efficiency

- Benchmarked countries using population-adjusted medal metrics.
- Revealed strong-performing nations beyond traditional medal rankings.
- Enabled fair comparison across countries of different sizes.

### Economic Impact

- Assessed relationships between GDP and Olympic performance.
- Observed positive trends between economic strength and medal success.
- Identified regional differences in Olympic competitiveness.

---

## 🚀 Business Impact

This project demonstrates how SQL and Power BI can be combined to transform raw datasets into actionable business intelligence solutions.

Key outcomes include:

- Performance benchmarking
- KPI monitoring
- Trend analysis
- Comparative reporting
- Interactive dashboard development
- Data-driven decision support

---

## 📷 Dashboard Preview

> Add your Power BI dashboard screenshot here.

```md
![Olympic Dashboard](dashboard.png)
```

---

## 📚 Skills Demonstrated

- SQL Reporting
- Data Analysis
- Data Modeling
- Power BI
- KPI Development
- Dashboard Design
- Window Functions
- Aggregate Functions
- CTEs
- Joins
- Analytical Reporting
- Business Intelligence

---

## 👩‍💻 Author

**Jennisha K**

Aspiring Data Analyst | SQL | Power BI | Excel | Python | Tableau

---
⭐ If you found this project useful, consider giving it a star.
