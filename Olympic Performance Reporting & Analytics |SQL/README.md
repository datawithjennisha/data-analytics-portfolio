# 🏅 Olympic Performance Analytics Dashboard

> Transforming Olympic data into actionable insights through SQL Reporting, KPI Analysis, and Interactive Power BI Dashboards.

---

## 📌 Project Overview

The Olympic Performance Analytics Dashboard is an end-to-end Business Intelligence project designed to analyze Olympic athlete performance, participation trends, medal efficiency, and the impact of economic indicators on sporting success.

Using a relational Olympic database consisting of athlete profiles, event participation records, medal achievements, country information, and economic statistics, the project demonstrates how advanced SQL reporting and Power BI visualization techniques can be used to convert raw data into meaningful business insights.

The solution combines data modeling, SQL analytics, KPI reporting, and interactive dashboard development to support performance benchmarking and strategic analysis. Through the use of Common Table Expressions (CTEs), Joins, Aggregate Functions, Window Functions, and KPI calculations, the project uncovers patterns that would otherwise remain hidden within large datasets.

This project simulates a real-world Business Intelligence workflow, beginning with data extraction and transformation, followed by analytical reporting and dashboard development to support data-driven decision-making.

---

## 🎯 Business Objectives

The primary objectives of this project were to:

* Identify the highest-performing Olympic athletes based on gold medal achievements.
* Analyze participation trends across Olympic events by gender.
* Evaluate Olympic success using population-adjusted medal efficiency metrics.
* Assess the relationship between economic strength and athletic performance.
* Develop KPI-driven analytical reports for performance monitoring.
* Design an interactive dashboard that enables users to explore Olympic performance from multiple perspectives.

---

## 🗄️ Data Model Overview

The project utilizes a relational database containing five interconnected tables:

### Athletes

Contains athlete demographic information including name, gender, age, height, and weight.

### Summer Games

Stores Summer Olympic event participation and medal achievements.

### Winter Games

Stores Winter Olympic event participation and medal achievements.

### Countries

Contains country and regional classification information.

### Country Statistics

Stores economic and demographic indicators including GDP, population, and Nobel Prize counts.

The relationships between these tables enable multi-dimensional analysis across athletes, countries, events, demographics, and economic factors.

---

## 📊 Dashboard Overview

The interactive Power BI dashboard was designed to provide a comprehensive view of Olympic performance through KPI monitoring, analytical reporting, and dynamic filtering capabilities.

### Dashboard KPIs

* Total Athletes
* Total Medals
* Total Gold Medals
* Countries Analyzed

### Interactive Filters

* Year
* Region
* Country
* Sport
* Gender

### Analytical Reports

# 📈 Analytical Reports

---

## 01. Top Athletes by Gold Medals

### Business Objective

Identify and rank the most successful Olympic athletes based on total Summer Olympic gold medals won.

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

### Skills Applied

* Common Table Expressions (CTEs)
* Joins
* Aggregate Functions
* Window Functions
* Ranking Functions

### Visualization

Horizontal Bar Chart

### Key Insight

The analysis identified the highest-performing Olympic athletes and highlighted the concentration of gold medal achievements among elite competitors.

---

## 02. Gender Participation by Event

### Business Objective

Analyze athlete participation trends across Olympic events by gender.

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

### Skills Applied

* Joins
* GROUP BY
* COUNT(DISTINCT)
* Demographic Analysis

### Visualization

100% Stacked Column Chart

### Key Insight

Participation analysis revealed variations in gender representation across sports and highlighted participation trends within Olympic events.

---

## 03. Country Medal Efficiency Analysis

### Business Objective

Benchmark Olympic success by calculating medals earned relative to country population size.

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

### Skills Applied

* KPI Reporting
* CTEs
* Joins
* Aggregate Functions
* Analytical Reporting

### Visualization

Clustered Column Chart

### Key Insight

Population-adjusted metrics revealed countries that achieved exceptional Olympic success relative to their size, enabling fairer performance comparisons.

---

## 04. GDP vs Olympic Performance Analysis

### Business Objective

Evaluate the relationship between economic strength and Olympic performance outcomes.

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

### Skills Applied

* CTEs
* Joins
* Aggregate Functions
* Comparative Analysis
* Business Intelligence Reporting

### Visualization

Scatter Plot

### Key Insight

The analysis suggested a positive relationship between economic strength and Olympic success, while also highlighting notable exceptions among countries and regions.


## 🔍 Key Findings

### 🏆 Athlete Performance Analysis

Athlete ranking analysis identified the most successful Olympic competitors based on cumulative gold medal achievements. SQL Window Functions were used to generate dynamic rankings, enabling performance comparison across athletes and events.

Key observations include:

* Elite athletes contribute disproportionately to total medal counts.
* Gold medal distribution is concentrated among a relatively small group of athletes.
* Ranking reports provide a clear framework for identifying top performers.

---

### 👥 Gender Participation Analysis

Participation analysis revealed variations in athlete representation across Olympic events.

Key observations include:

* Certain sports exhibit stronger participation from one gender.
* Participation distribution varies significantly across events.
* Gender-based reporting helps identify demographic engagement patterns.

---

### 🌍 Country Medal Efficiency Analysis

Traditional medal rankings often favor highly populated countries. To address this limitation, medal efficiency metrics were calculated using medals per million population.

Key observations include:

* Several smaller nations demonstrated exceptional Olympic efficiency.
* Population-adjusted metrics provide a more balanced assessment of performance.
* Normalized comparisons reveal strong-performing countries that may not rank highly by total medal count alone.

---

### 📈 Economic Impact Analysis

Economic indicators were analyzed to evaluate their relationship with Olympic success.

Key observations include:

* Regions with stronger GDP levels generally achieved higher medal counts.
* Economic resources may contribute positively to athlete development and sports infrastructure.
* Significant regional variations exist in Olympic competitiveness and investment capacity.

---

## 🚀 Business Impact

This project demonstrates how modern analytics solutions can transform complex datasets into actionable intelligence.

The techniques applied in this project closely mirror real-world Business Intelligence and Data Analytics workflows used across industries for performance measurement, KPI tracking, benchmarking, and strategic decision-making.

Business value delivered includes:

* Performance Benchmarking
* KPI Monitoring
* Comparative Analysis
* Trend Identification
* Executive Reporting
* Interactive Dashboarding
* Data-Driven Decision Support

The project showcases the practical application of SQL and Power BI to solve analytical problems and generate business insights from large relational datasets.

---

## 📚 Skills Demonstrated

### SQL

* Common Table Expressions (CTEs)
* Joins
* Aggregate Functions
* Window Functions
* Ranking Functions
* Analytical Queries
* KPI Calculations

### Power BI

* Data Modeling
* Relationships
* DAX Measures
* Interactive Dashboards
* KPI Cards
* Slicers & Filters
* Business Intelligence Reporting

### Analytics

* Performance Analysis
* Trend Analysis
* Demographic Analysis
* Benchmarking
* Data Visualization
* Business Intelligence

---

## 👩‍💻 Author

**Jennisha K**

Data Analyst | SQL | Power BI | Python | Tableau | Excel

Passionate about transforming data into actionable insights through analytics, reporting, and visualization.
