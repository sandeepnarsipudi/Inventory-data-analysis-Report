
Inventory Data Analysis Dashboard (Power BI + SQL Server+ SQL Database)

Dashboard Link: https://app.powerbi.com/view?r=eyJrIjoiNDQyMmFkMjgtNTcyZC00M2RjLTkyMmQtN2RiMDM5NTBjNTE3IiwidCI6IjIzODk2NDkwLTdlNzMtNGQ1Zi1hZjQ5LTBmMjUwMzQ5NWQ3NSJ9&pageName=87d6d553e672994f2250

Dashboard Overview

This project showcases an **Inventory Data Analysis Dashboard** built using **Power BI**, focusing on demand, availability, supply shortages, profit, and loss metrics.

A key highlight of this project is the **data source migration capability**:

* Initially connected to a **SQL Server (on-prem / local SQL instance)**
* Later migrated to a **SQL Database (separate environment)**
* Without changing or rebuilding the existing Power BI report**

This demonstrates strong understanding of **Power BI data source flexibility** and real-world **environment migration handling**.

The dashboard consists of **two simple analytical pages** designed for quick business insights.

---

Problem Statement

Inventory systems often move across environments (development, test, production). Reports should remain stable even when backend databases change.

This project demonstrates how Power BI dashboards can continue to function **without rework** when the data source changes from **SQL Server to SQL Database**.

Using this dashboard, users can:

* Monitor demand vs availability
* Identify supply shortages
* Track profit and loss
* Analyze daily inventory performance
* Switch SQL environments without redesigning reports

---

Tools & Technologies Used

* **Power BI Desktop**
* **SQL Server**
* **SQL Database**
* **DAX (Data Analysis Expressions)**
* **SQL-based data cleaning**
* **Environment migration (SQL Server → SQL Database)**

---

Steps Followed

Data Preparation & Source Migration

* **Step 1:** Inventory data was initially sourced from **SQL Server**.
* **Step 2:** Performed basic data cleaning and corrections in **SQL Server**.
* **Step 3:** Migrated the same dataset to a **SQL Database** (separate environment).
* **Step 4:** Updated the Power BI data source connection to the SQL Database.
* **Step 5:** Verified that **all visuals, filters, and DAX measures remained intact** without report redesign.

Report Design

* Step 6:** Created **two report pages**:

  * Inventory Overview
  * Inventory Performance Metrics
* **Step 7:** Added KPI cards and visuals to highlight demand, availability, shortages, profit, and loss.

---

DAX Measures Used

> The following **9 DAX measures** were created and used in this project.

Inventory Measures

```DAX
Total Demand =
SUM ( Inventory[demand] )
```

```DAX
Total Availability =
SUM ( Inventory[availability] )
```

```DAX
Average Demand per Day =
AVERAGE ( Inventory[demand] )
```

```DAX
Average Availability per Day =
AVERAGE ( Inventory[availability] )
```

---

Supply & Shortage Measures

```DAX
Supply Shortage =
SUMX (
    Inventory,
    MAX ( Inventory[demand] - Inventory[availability], 0 )
)
```

```DAX
Total Supply Shortage =
[Supply Shortage]
```

---

Financial Measures

```DAX
Total Profit =
SUMX (
    Inventory,
    Inventory[availability] * Inventory[unit_price]
)
```

```DAX
Total Loss =
SUMX (
    Inventory,
    [Supply Shortage] * Inventory[unit_price]
)
```

```DAX
Average Daily Loss =
DIVIDE (
    [Total Loss],
    DISTINCTCOUNT ( Inventory[Order_Date_DD_MM_YYYY] ),
    0
)
```

---

Key Insights

* Seamless migration from **SQL Server to SQL Database** without impacting the report.
* Inventory gaps directly contribute to supply shortages and financial loss.
* Profit and loss metrics provide actionable operational insights.
* Demonstrates environment-agnostic Power BI report design.

---

Conclusion

This project highlights real-world Power BI expertise in handling **backend SQL environment changes** without report redevelopment. It demonstrates strong skills in SQL, DAX, and Power BI architecture suitable for production-grade analytics solutions.

