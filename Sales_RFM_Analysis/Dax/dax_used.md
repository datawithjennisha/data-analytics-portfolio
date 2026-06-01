---

## 🧮 DAX — Full Reference

---

### 📁 Tbl_Measure Table — KPI Measures

> 🔵 These are **measures** stored in the `Tbl_Measure` table.

```dax
MaxOrderDate = MAX('Superstore 2025'[Order Date])
```

```dax
Total Customers = DISTINCTCOUNT('Superstore 2025'[Customer ID])
```

```dax
Total Sales = SUM('Superstore 2025'[Sales])
```

```dax
AvgRecency = AVERAGE(RFM_Calculation[Recency])
```

```dax
AvgFrequency = AVERAGE(RFM_Calculation[Frequency])
```

```dax
AvgMonetary = AVERAGE(RFM_Calculation[Monetary])
```

---

### 📈 YoY Variance Measures

> 🔵 Dynamic text measures showing Year-over-Year change with ▲ ▼ indicators.

```dax
YoY SalesVariance =
 VAR LY = CALCULATE([Total Sales], SAMEPERIODLASTYEAR(DateTable[Date]))
 VAR LYFormatted = FORMAT(LY/1000, "$#,0") & "K"
 VAR yoyCalc = DIVIDE([Total Sales] - LY, LY)
 VAR yoyCalcFormatted = FORMAT(yoyCalc, "0.0%; (0.0%)")
 RETURN
  SWITCH(
    TRUE(),
    yoyCalc > 0,   UNICHAR(9650) & " " & yoyCalcFormatted & " | LY " & LYFormatted,
    ISBLANK(LY),   UNICHAR(8211) & " | No Data for Last Year",
    yoyCalc = 0,   UNICHAR(8211) & " | No Change from Last Year",
                   UNICHAR(9660) & " " & yoyCalcFormatted & " | LY " & LYFormatted)
```

```dax
YoY FrequencyVar =
 VAR LY = CALCULATE([AvgFrequency], SAMEPERIODLASTYEAR(DateTable[Date]))
 VAR LYFormatted = FORMAT(LY, "#,0")
 VAR yoyCalc = DIVIDE(([AvgFrequency] - LY), LY)
 VAR yoyCalcFormatted = FORMAT(yoyCalc, "0.0%;(0.0%)")
 RETURN
  SWITCH(
    TRUE(),
    yoyCalc > 0,   UNICHAR(9650) & " " & yoyCalcFormatted & " | LY " & LYFormatted,
    ISBLANK(LY),   UNICHAR(8211) & " | No Data for Last Year ",
                   UNICHAR(9660) & " " & yoyCalcFormatted & " | LY " & LYFormatted)
```

```dax
YoY MonetaryVar =
 VAR LY = CALCULATE([AvgMonetary], SAMEPERIODLASTYEAR(DateTable[Date]))
 VAR LYFormatted = FORMAT(LY/1000, "$#,0.00") & "K"
 VAR yoyCalc = DIVIDE(([AvgMonetary] - LY), LY)
 VAR yoyCalcFormatted = FORMAT(yoyCalc, "0.0%;(0.0%)")
 RETURN
  SWITCH(
    TRUE(),
    yoyCalc > 0,   UNICHAR(9650) & " " & yoyCalcFormatted & " | LY " & LYFormatted,
    ISBLANK(LY),   UNICHAR(8211) & " | No Data for Last Year ",
                   UNICHAR(9660) & " " & yoyCalcFormatted & " | LY " & LYFormatted)
```

```dax
YoY RecencyVar =
 VAR LY = CALCULATE([AvgRecency], SAMEPERIODLASTYEAR(DateTable[Date]))
 VAR LYFormatted = FORMAT(LY, "#,0")
 VAR yoyCalc = DIVIDE(([AvgRecency] - LY), LY)
 VAR yoyCalcFormatted = FORMAT(yoyCalc, "0.0%;(0.0%)")
 RETURN
  SWITCH(
    TRUE(),
    yoyCalc > 0,   UNICHAR(9650) & " " & yoyCalcFormatted & " | LY " & LYFormatted,
    ISBLANK(LY),   UNICHAR(8211) & " | No Data for Last Year ",
                   UNICHAR(9660) & " " & yoyCalcFormatted & " | LY " & LYFormatted)
```

---

### 🎨 Dynamic YoY Color Measures

> 🟢 Green = improvement &nbsp;|&nbsp; 🔴 Red = decline &nbsp;|&nbsp; 🟠 Orange = no prior year data

```dax
salesYoYColor =
 VAR LY  = CALCULATE([Total Sales], SAMEPERIODLASTYEAR(DateTable[Date]))
 VAR YOY = DIVIDE([Total Sales] - LY, LY)
 RETURN SWITCH(TRUE(),
    YOY > 0,              "#00B200",
    OR(ISBLANK(LY),LY=0), "Orange",
                          "#FF0000")
```

```dax
FrequencyYoYColor =
 VAR LY  = CALCULATE([AvgFrequency], SAMEPERIODLASTYEAR(DateTable[Date]))
 VAR YOY = DIVIDE([AvgFrequency] - LY, LY)
 RETURN SWITCH(TRUE(),
    YOY > 0,              "#00B200",
    OR(ISBLANK(LY),LY=0), "Orange",
                          "#FF0000")
```

```dax
monetaryYoYColor =
 VAR LY  = CALCULATE([AvgMonetary], SAMEPERIODLASTYEAR(DateTable[Date]))
 VAR YOY = DIVIDE([AvgMonetary] - LY, LY)
 RETURN SWITCH(TRUE(),
    YOY > 0,              "#00B200",
    OR(ISBLANK(LY),LY=0), "Orange",
                          "#FF0000")
```

```dax
recencyYoYColor =
 VAR LY  = CALCULATE([AvgRecency], SAMEPERIODLASTYEAR(DateTable[Date]))
 VAR YOY = DIVIDE([AvgRecency] - LY, LY)
 RETURN SWITCH(TRUE(),
    YOY > 0,              "#00B200",
    OR(ISBLANK(LY),LY=0), "Orange",
                          "#FF0000")
```

---

### 📅 DateTable — Calculated Table

> 🟣 This is a **calculated table** created using DAX in the Data Model.

```dax
DateTable =
ADDCOLUMNS (
    CALENDAR(DATE(2021,1,1), DATE(2025,12,31)),
    "Year",         YEAR([Date]),
    "Month Number", MONTH([Date]),
    "Month Name",   FORMAT([Date], "MMMM"),
    "Year-Month",   FORMAT([Date], "YYYY-MM"),
    "Quarter",      "Q" & FORMAT([Date], "Q"),
    "Day",          DAY([Date]),
    "Day of Week",  WEEKDAY([Date], 2),
    "Day Name",     FORMAT([Date], "dddd"),
    "Week Number",  WEEKNUM([Date], 2)
)
```

---

### 🧮 RFM_Calculation — Calculated Table

> 🟣 This is a **calculated table** — summarises one row per customer with Recency, Frequency, Monetary values.

```dax
RFM_Calculation =
SUMMARIZE(
    'Superstore 2025',
    'Superstore 2025'[Customer ID],
    'Superstore 2025'[Customer Name],
    "Recency",   DATEDIFF(
                    CALCULATE(MAX('Superstore 2025'[Order Date])),
                    CALCULATE(MAX('Superstore 2025'[Order Date]), ALL('Superstore 2025')),
                    DAY),
    "Frequency", DISTINCTCOUNT('Superstore 2025'[Order ID]),
    "Monetary",  SUM('Superstore 2025'[Sales])
)
```

---

### 🏷️ Calculated Columns — inside RFM_Calculation Table

> 🟡 These are **calculated columns** added directly inside the `RFM_Calculation` table. They are evaluated row by row.

**Recency_Score** — Ranks customers by recency (lower days = better score)
```dax
Recency_Score =
 VAR RankRecency = RANKX(ALL(RFM_Calculation), RFM_Calculation[Recency],, ASC)
 VAR TotalCust   = COUNTROWS(ALL(RFM_Calculation))
 RETURN CEILING(DIVIDE(RankRecency * 5, TotalCust), 1)
```

**Frequency_Score** — Ranks customers by order count (higher = better score)
```dax
Frequency_Score =
 VAR RankFreq  = RANKX(ALL(RFM_Calculation), RFM_Calculation[Frequency],, DESC)
 VAR TotalCust = COUNTROWS(ALL(RFM_Calculation))
 RETURN CEILING(DIVIDE(RankFreq * 5, TotalCust), 1)
```

**Monetary_Score** — Ranks customers by total spend (higher = better score)
```dax
Monetary_Score =
 VAR RankMon   = RANKX(ALL(RFM_Calculation), RFM_Calculation[Monetary],, DESC)
 VAR TotalCust = COUNTROWS(ALL(RFM_Calculation))
 RETURN CEILING(DIVIDE(RankMon * 5, TotalCust), 1)
```

**Customer_Segment** — Assigns final segment label based on score combinations
```dax
Customer_Segment =
SWITCH(
    TRUE(),
    -- 🏆 Champions: best across all 3 dimensions
    RFM_Calculation[Recency_Score]   <= 2 &&
    RFM_Calculation[Frequency_Score] <= 2 &&
    RFM_Calculation[Monetary_Score]  <= 2,  "Champions",

    -- 💎 Loyal Customers: frequent and fairly recent
    RFM_Calculation[Frequency_Score] <= 2 &&
    RFM_Calculation[Recency_Score]   <= 3,  "Loyal Customers",

    -- 💸 Big Spenders: high spend but not recent
    RFM_Calculation[Monetary_Score]  <= 2 &&
    RFM_Calculation[Recency_Score]   >= 3,  "Big Spenders",

    -- ⚠️ At Risk: used to buy often but recency is dropping
    RFM_Calculation[Recency_Score]   >= 3 &&
    RFM_Calculation[Frequency_Score] <= 3,  "At Risk",

    -- 📉 Lost: worst scores across all 3 metrics
    RFM_Calculation[Recency_Score]   =  5 &&
    RFM_Calculation[Frequency_Score] =  5 &&
    RFM_Calculation[Monetary_Score]  =  5,  "Lost",

    -- 🔵 Default
    "Others"
)
```

---

### 📌 DAX Object Types — Quick Reference

| Symbol | Type | What It Is |
|---|---|---|
| 🔵 | **Measure** | Calculated at query time, context-aware, stored in Measure table |
| 🟣 | **Calculated Table** | Created once at refresh, lives in the data model |
| 🟡 | **Calculated Column** | Row-level computation, stored inside a table |

---
