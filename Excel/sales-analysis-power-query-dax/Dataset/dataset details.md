# 📂 Dataset Details

| Sheet Name | Description | Key Columns | Data Types |
|---|---|---|---|
| **FactInternetSales** | Main transactional sales dataset containing revenue, quantity, cost, and order details | ProductKey, CustomerKey, SalesAmount, OrderQuantity, OrderDate | Integer, Decimal, Date, Text |
| **DimProduct** | Product information including category, pricing, and manufacturing details | ProductKey, ProductName, StandardCost, ListPrice | Integer, Decimal, Text |
| **DimSalesTerritory** | Sales region and territory information | SalesTerritoryKey, Region, Country | Integer, Text |
| **DimDate** | Calendar and time intelligence dimension table | DateKey, MonthName, CalendarQuarter, CalendarYear | Integer, Date, Text |
| **DimCustomer** | Customer demographic and purchase information | CustomerKey, Gender, Income, Occupation | Integer, Date, Text |
| **DimGeography** | Geographic and location-based customer information | GeographyKey, City, Country, PostalCode | Integer, Text |

---

# 📊 FactInternetSales — Transaction Dataset

| Column Name | Data Type |
|---|---|
| ProductKey | Integer |
| CustomerKey | Integer |
| OrderQuantity | Integer |
| UnitPrice | Decimal |
| SalesAmount | Decimal |
| TotalProductCost | Decimal |
| TaxAmt | Decimal |
| Freight | Decimal |
| OrderDate | Date |
| ShipDate | Date |
| SalesOrderNumber | Text |

---

# 🛍️ DimProduct — Product Information

| Column Name | Data Type |
|---|---|
| ProductKey | Integer |
| ProductAlternateKey | Text |
| EnglishProductName | Text |
| StandardCost | Decimal |
| ListPrice | Decimal |
| Weight | Decimal |
| Status | Text |
| StartDate | Date |

---

# 🌍 DimSalesTerritory — Sales Region Details

| Column Name | Data Type |
|---|---|
| SalesTerritoryKey | Integer |
| SalesTerritoryRegion | Text |
| SalesTerritoryCountry | Text |
| SalesTerritoryGroup | Text |

---

# 📅 DimDate — Date Dimension Table

| Column Name | Data Type |
|---|---|
| DateKey | Integer |
| FullDateAlternateKey | Date |
| EnglishDayNameOfWeek | Text |
| EnglishMonthName | Text |
| CalendarQuarter | Integer |
| CalendarYear | Integer |
| FiscalQuarter | Integer |
| FiscalYear | Integer |

---

# 👥 DimCustomer — Customer Information

| Column Name | Data Type |
|---|---|
| CustomerKey | Integer |
| GeographyKey | Integer |
| FirstName | Text |
| LastName | Text |
| BirthDate | Date |
| Gender | Text |
| YearlyIncome | Integer |
| Occupation | Text |
| DateFirstPurchase | Date |

---

# 🌐 DimGeography — Geographic Information

| Column Name | Data Type |
|---|---|
| GeographyKey | Integer |
| City | Text |
| StateProvinceName | Text |
| CountryRegionCode | Text |
| EnglishCountryRegionName | Text |
| PostalCode | Integer |
