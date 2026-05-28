<div align="center">

# 🌍 PRODIGY\_DS\_01 — World Population Distribution

### Interactive Power BI Dashboard | Prodigy InfoTech Data Science Internship — Task 01

[![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![World Bank Data](https://img.shields.io/badge/World%20Bank-Open%20Data-blue?style=for-the-badge)](https://data.worldbank.org/indicator/SP.POP.TOTL)
[![Internship](https://img.shields.io/badge/Prodigy%20InfoTech-Internship-orange?style=for-the-badge)](https://prodigyinfotech.dev/)

> Analyzing global population trends across **266 countries and regions (1960–2024)** using the World Bank Population Dataset.

</div>

---

## 📋 Table of Contents

- [Project Overview](#-project-overview)
- [Internship Details](#-internship-details)
- [Dataset Information](#-dataset-information)
- [Dashboard Screenshots](#-dashboard-screenshots)
- [Detailed Working & How It Works](#-detailed-working--how-it-works)
- [How to Use the Dashboard](#-how-to-use-the-dashboard)
- [Data Cleaning & Transformation](#-data-cleaning--transformation)
- [DAX Measures Used](#-dax-measures-used)
- [Key Findings](#-key-findings)
- [Project Structure](#-project-structure)
- [How to Run the Project](#-how-to-run-the-project)
- [Learning Outcomes](#-learning-outcomes)
- [Embedded Report](#-embedded-report)
- [Author](#-author)

---

## 📌 Project Overview

This project visualizes and analyzes **world population distribution** across countries and regions over time using **interactive Power BI dashboards**. The report provides deep insights into:

- 📈 Population growth trends from **1960–2024**
- 🏆 Most populous countries in **2023**
- 🌐 **Region-wise** population contribution
- 📊 Population distribution by **country groups**
- 🎛️ Interactive filtering using **year slicers**

---

## 🏢 Internship Details

| Field | Details |
|---|---|
| **Internship** | Prodigy InfoTech |
| **Track** | Data Science |
| **Task** | Task 01 — Data Visualization |
| **Intern** | Siddhi Sharma |
| **Tool Used** | Power BI Desktop |

---

## 📂 Dataset Information

| Property | Details |
|---|---|
| **Source** | World Bank Open Data |
| **Indicator** | Population, Total (`SP.POP.TOTL`) |
| **Coverage** | 266 Countries & Regions |
| **Time Range** | 1960 – 2024 |
| **Link** | [data.worldbank.org](https://data.worldbank.org/indicator/SP.POP.TOTL) |

The dataset contains **one row per country per year**, with columns for Country Name, Country Code, Indicator Name, Indicator Code, and annual population values from 1960 onwards. It was downloaded as a `.csv` from the World Bank portal and imported directly into Power BI Desktop.

---

## 📊 Dashboard Screenshots
![OVERALL DASHBOARD](https://raw.githubusercontent.com/siddhisharmaup85-web/PRODIGY_DS_01/main/screenshots/OVERALL_DASHBOARD.png)

---

### 1️⃣ Top 10 Most Populous Countries (2023)
![Top 10 Most Populous Countries](https://raw.githubusercontent.com/siddhisharmaup85-web/PRODIGY_DS_01/main/screenshots/Chart1_top_10_most_populous_countries_2023.png)

> Horizontal bar chart showing countries ranked by population in 2023. India leads with over **1.4 billion** people, surpassing China for the first time.

---

### 2️⃣ Population Distribution by Group (Histogram)
![Population Distribution by Group](https://raw.githubusercontent.com/siddhisharmaup85-web/PRODIGY_DS_01/main/screenshots/Chart3_count_of_country_name_by_population_group.png)

> Countries are grouped into population buckets (Under 10M → Above 500M). The vast majority of countries fall below **10 million**, while only 2 countries exceed **500 million**.

---

### 3️⃣ World Population Growth (1960–2024)
![World Population Growth](https://raw.githubusercontent.com/siddhisharmaup85-web/PRODIGY_DS_01/main/screenshots/Chart4_sum_of_population_by_year.png)

> Line chart showing steady global population growth over six decades. The world crossed **8 billion** in 2022, with the steepest growth occurring between 1980 and 2010.

---

### 4️⃣ Population by Region
![Population by Region](https://raw.githubusercontent.com/siddhisharmaup85-web/PRODIGY_DS_01/main/screenshots/Chart2_sum_of_population_by_region.png)

> Regional breakdown of population. **South Asia** and **East Asia & Pacific** dominate, while regions like **North America** and **Middle East & North Africa** contribute comparatively smaller shares.

---

### 5️⃣ KPI Cards — Summary Metrics
![KPI Cards](https://raw.githubusercontent.com/siddhisharmaup85-web/PRODIGY_DS_01/main/screenshots/KPI_CARDS.png)

> At-a-glance summary cards showing:
> - 🌍 Total World Population (dynamically updated by slicer)
> - 🌎 Number of Countries/Regions tracked (266)
> - 🏳️ Selected Country Name (context-aware)

---

### 6️⃣ Interactive Year Slicer
![Interactive Year Slicer](https://raw.githubusercontent.com/siddhisharmaup85-web/PRODIGY_DS_01/main/screenshots/Slicer_Fitter_according_to_year.png)

> A dynamic year-range slicer allows filtering the entire dashboard by any year or range from 1960–2024. All visuals update in real time when the slicer is adjusted.

---

## 📊 Data Used
![Data Used](https://raw.githubusercontent.com/siddhisharmaup85-web/PRODIGY_DS_01/main/screenshots/DATA_USED.png)

---

## 🤝 Detailed Working & How It Works

---


### Step-by-Step Data Pipeline

```
World Bank CSV  →  Power Query (ETL)  →  Data Model  →  DAX Measures  →  Visuals  →  Dashboard
```

### 1. Data Ingestion
- The World Bank dataset is downloaded as a `.csv` file.
- Imported into **Power BI Desktop** via `Home → Get Data → Text/CSV`.
- Power BI automatically detects column data types on import.

### 2. Power Query — ETL (Extract, Transform, Load)

All cleaning and reshaping happens inside **Power Query Editor** before data reaches the model:

| Step | Action | Why |
|---|---|---|
| Remove Nulls | Filtered out rows where Population = blank | Prevents incorrect totals |
| Rename Columns | `Country Name` → `Country`, `Value` → `Population` | Cleaner field names |
| Data Type Conversion | Population column → Whole Number | Enables SUM aggregation |
| Unpivot Years | Pivoted year columns into a single `Year` column | Normalized table structure |
| Custom Groups | Created `Population Group` column with IF/SWITCH logic | Enables histogram bucketing |
| Merge Metadata | Joined region data from a second table on `Country Code` | Enables region-wise analysis |
| Remove Redundant Columns | Dropped Indicator Name, Indicator Code | Reduces model size |

### 3. Data Model
- The cleaned table is loaded into the **Power BI Data Model**.
- Relationships are automatically detected between the fact table and any lookup tables.
- The model follows a **star schema** pattern — one fact table (population values) surrounded by dimension-like columns (Country, Year, Region).

### 4. DAX Calculations
Custom **DAX (Data Analysis Expressions)** measures power the KPI cards and dynamic visuals:

```dax
// Total Population — sums all population values in current filter context
Total Population = SUM('Table'[Population])

// Country Count — counts distinct countries in current filter context
Country Count = DISTINCTCOUNT('Table'[Country Name])
```

These measures respond dynamically to any slicer or filter applied on the dashboard page.

### 5. Visual Construction

| Visual | Chart Type | Fields Used |
|---|---|---|
| Top 10 Countries | Horizontal Bar Chart | Country (Axis), Total Population (Value), Top N Filter = 10 |
| Population Groups | Column Chart / Histogram | Population Group (Axis), Country Count (Value) |
| Growth Over Time | Line Chart | Year (Axis), Total Population (Value) |
| Region-wise | Horizontal Bar Chart | Region (Axis), Total Population (Value) |
| KPI Cards | Card Visual | Total Population, Country Count, Selected Country |
| Year Filter | Slicer Visual | Year (Field), Range slider type |

### 6. Interactivity
- All visuals are **cross-filtered** — clicking any bar/region filters every other visual on the page.
- The **Year Slicer** filters the entire report page simultaneously.
- The **Top N filter** on the bar chart ensures only the top 10 countries are always shown regardless of year selected.

---

## 🤝 How to Use the Dashboard

### Basic Navigation

1. **Open the `.pbix` file** in Power BI Desktop (or view the PDF report below for a static snapshot).
2. The dashboard loads on **Page 1** showing all visuals for the default year range.

### Using the Year Slicer
- Drag the **left handle** of the slicer to set the start year (e.g., 2000).
- Drag the **right handle** to set the end year (e.g., 2023).
- All KPI cards, bar charts, and line chart update **instantly**.
- To reset, drag both handles back to the full range (1960–2024).

### Cross-Filtering Visuals
- **Click a bar** in the Top 10 chart → all other visuals filter to show data for only that country.
- **Click a region** in the Region chart → Top 10 and growth line filter to that region only.
- **Click empty space** anywhere to clear the filter selection.

### KPI Cards
- The **Total Population card** reflects the sum for the currently filtered context (e.g., if you select India, it shows India's population).
- The **Country Count card** shows how many countries are included in the current filter.
- The **Selected Country card** displays the name of the country selected via cross-filtering.

### Reading the Population Groups Histogram
- The X-axis shows population brackets (Under 10M, 10M–50M, 50M–100M, 100M–500M, Above 500M).
- The Y-axis shows how many countries fall into each bracket.
- Use the year slicer to see how countries shift between brackets over decades.


---
 
## 🤝 Data Cleaning & Transformation
 
All data cleaning and transformation was performed inside **Power Query Editor** in Power BI Desktop before loading data into the model. Below is a detailed breakdown of every step applied.
 
---
 
### Step 1 — Import Raw CSV
 
The raw World Bank CSV file has a wide format — **one column per year** (1960, 1961, … 2024) — which is not suitable for Power BI's column-based aggregations.
 
```
Raw Structure:
| Country Name | Country Code | Indicator Name | Indicator Code | 1960 | 1961 | ... | 2024 |
```
 
---
 
### Step 2 — Remove Unnecessary Columns
 
The columns `Indicator Name` and `Indicator Code` carry the same value in every row (`SP.POP.TOTL`) and add no analytical value.
 
```
Removed: [Indicator Name], [Indicator Code]
Kept: [Country Name], [Country Code], [1960] … [2024]
```
 
---
 
### Step 3 — Unpivot Year Columns (Wide → Long Format)
 
This is the most critical transformation. All year columns (1960–2024) are **unpivoted** into two new columns:
 
```
Before Unpivot:
| Country Name | 1960       | 1961       | ... |
| India        | 450000000  | 460000000  | ... |
 
After Unpivot:
| Country Name | Year | Population  |
| India        | 1960 | 450000000   |
| India        | 1961 | 460000000   |
```
 
**How to unpivot in Power Query:**
> Select all year columns → Right-click → `Unpivot Columns`
> Rename the auto-generated `Attribute` column → `Year`
> Rename the auto-generated `Value` column → `Population`
 
---
 
### Step 4 — Fix Data Types
 
After unpivoting, Power Query treats `Year` as text and `Population` as text. Both must be corrected:
 
| Column | From | To | Reason |
|---|---|---|---|
| `Year` | Text | Whole Number | Enables time-axis sorting and slicer range |
| `Population` | Text | Whole Number | Enables SUM aggregation in DAX |
| `Country Name` | Text | Text (unchanged) | Already correct |
| `Country Code` | Text | Text (unchanged) | Used as join key |
 
---
 
### Step 5 — Handle Null / Blank Values
 
Some country-year combinations have **no population data** (blank cells in the original CSV). These are removed to prevent incorrect totals and aggregation errors.
 
```
Filter Applied: Keep rows where [Population] is not null and not blank
```
 
> ⚠️ This particularly affects data from the 1960s for newly formed nations and territories with incomplete historical records.
 
---
 
### Step 6 — Add Custom Column: Population Group
 
A calculated column is added in Power Query using **IF/SWITCH logic** to bucket each row into a population category. This powers the histogram visual.
 
```m
// M Language (Power Query)
= if [Population] < 10000000 then "Under 10M"
  else if [Population] < 50000000 then "10M – 50M"
  else if [Population] < 100000000 then "50M – 100M"
  else if [Population] < 500000000 then "100M – 500M"
  else "Above 500M"
```
 
| Group Label | Population Range |
|---|---|
| Under 10M | < 10,000,000 |
| 10M – 50M | 10,000,000 – 49,999,999 |
| 50M – 100M | 50,000,000 – 99,999,999 |
| 100M – 500M | 100,000,000 – 499,999,999 |
| Above 500M | ≥ 500,000,000 |
 
---
 
### Step 7 — Merge Region Metadata
 
The World Bank CSV does not include a `Region` column. Region information is available in a **separate metadata CSV** (`Metadata_Country.csv`) also provided by the World Bank.
 
```
Merge Type: Left Join
Join Key: [Country Code]
Added Column: [Region]
```
 
This enables the **"Population by Region"** bar chart visual.
 
---
 
### Step 8 — Rename & Clean Column Names
 
All column names are cleaned for readability and consistency inside Power Query:
 
| Original Name | Renamed To |
|---|---|
| `Country Name` | `Country` |
| `Value` | `Population` |
| `Attribute` | `Year` |
 
---
 

## 🛠 Tools & Technologies Used

| Tool | Purpose |
|---|---|
| **Power BI Desktop** | Dashboard development & publishing |
| **Power Query (M Language)** | Data cleaning, transformation, and ETL |
| **DAX** | Custom measures and KPI calculations |
| **World Bank Open API/CSV** | Source data |
| **Interactive Slicers** | User-driven filtering |

---

## 📈 DAX Measures Used

```dax
// Aggregates total population across all rows in current filter context
Total Population = SUM('Table'[Population])

// Counts how many unique countries are in the current view
Country Count = DISTINCTCOUNT('Table'[Country Name])
```

Both measures are **context-aware** — their output changes dynamically based on which year, country, or region is selected via slicers or cross-filters.

---

## 🔍 Key Findings

- 🇮🇳 **India** became the world's most populous country in 2023, surpassing China with **1.4+ billion** people.
- 🌐 **Global population crossed 8 billion** in 2022, marking a historic milestone.
- 🏘️ **Over 100 countries** (more than a third of all nations) have populations below 10 million — the world is demographically highly concentrated.
- 🌏 **South Asia** and **East Asia & Pacific** together account for more than **half** of global population.
- 📈 The steepest phase of global population growth occurred between **1980 and 2010**, after which the growth rate began gradually slowing.
- 🌍 Only **2 entities** (India and China) exceed 500 million — the rest of the world's 264 countries are below that threshold.

---

## 🎨 Dashboard Features

| Feature | Status |
|---|---|
| Interactive Cross-Filtering | ✅ |
| Dynamic Year Slicer (1960–2024) | ✅ |
| KPI Cards with Context-Aware Measures | ✅ |
| Top 10 Filter (Auto-Updated) | ✅ |
| Region-wise Breakdown | ✅ |
| Population Group Histogram | ✅ |
| Trend Line Chart (64 years) | ✅ |
| Professional Dashboard Design | ✅ |

---

## 📁 Project Structure

```bash
PRODIGY_DS_01/
│
├── PRODIGY_DS_01.pbix             # Power BI report file (open in Power BI Desktop)
├── PRODIGY_DS_01_Report.pdf       # Static PDF export of the full dashboard
├── README.md                      # This file
│
└── screenshots/
    ├── top10_population.png       # Top 10 most populous countries (2023)
    ├── population_groups.png      # Histogram — countries by population bracket
    ├── population_growth.png      # Line chart — world population 1960–2024
    ├── population_region.png      # Regional population distribution
    ├── kpi_cards.png              # KPI summary cards
    └── slicer.png                 # Year range slicer
```

---

## 🚀 How to Run the Project

### Prerequisites
- [Power BI Desktop](https://powerbi.microsoft.com/en-us/desktop/) (free download from Microsoft)
- Windows OS (Power BI Desktop is Windows-only)

### Steps

**Step 1 — Clone the Repository**
```bash
git clone https://github.com/siddhisharmaup85-web/PRODIGY_DS_01.git
cd PRODIGY_DS_01
```

**Step 2 — Open in Power BI**
```
Double-click PRODIGY_DS_01.pbix
  → Opens directly in Power BI Desktop
```

**Step 3 — Refresh Data (Optional)**
```
Home tab → Refresh
  → Re-fetches the dataset if the source path is configured
  → Skip if you just want to explore the existing visuals
```

**Step 4 — Interact with the Dashboard**
- Use the **year slicer** to filter by time period
- **Click any visual** to cross-filter the entire dashboard
- Hover over bars/points to see **tooltips** with exact figures

**Step 5 — Export (Optional)**
```
File → Export → Export to PDF
  → Generates a static PDF snapshot of the current dashboard state
```

---

## 📖 Embedded Report

> 📄 **View the full static dashboard report as a PDF:**

🔗 [**Open Full Report PDF →**](https://github.com/siddhisharmaup85-web/PRODIGY_DS_01/blob/4e9c8e45e7a7271c5456b6b1a6968108f93d66ad/PRODIGY_DS_01_Report.pdf)
[![PDF Preview](https://raw.githubusercontent.com/siddhisharmaup85-web/PRODIGY_DS_01/main/screenshots/OVERALL_DASHBOARD.png)](https://github.com/siddhisharmaup85-web/PRODIGY_DS_01/blob/4e9c8e45e7a7271c5456b6b1a6968108f93d66ad/PRODIGY_DS_01_Report.pdf)


*The PDF includes all 6 dashboard visuals exported at full resolution — useful for quick reference without opening Power BI Desktop.*

---

## 📚 Learning Outcomes

Through this project, I developed hands-on proficiency in:

- **Power BI Dashboard Development** — building multi-visual, interactive report pages from scratch
- **Power Query (ETL)** — cleaning, reshaping, and transforming raw CSV data into a structured model
- **DAX Calculations** — writing context-aware measures for KPI cards and dynamic aggregations
- **Data Visualization Principles** — choosing the right chart type for the right data story (bar, line, histogram, card)
- **Interactive Report Design** — configuring slicers, cross-filters, and Top N filters for user-driven exploration
- **Data Storytelling** — translating raw population numbers into clear, insightful narratives

---

## 🤝 Acknowledgements

- **Prodigy InfoTech** — for the internship task and learning framework
- **World Bank Open Data** — for the publicly available population dataset
- **Microsoft Power BI** — for the free, powerful visualization platform

---

## 🤝 Author

### Siddhi Sharma
**B.Tech CSE Student | Data Science Enthusiast**

[![GitHub](https://img.shields.io/badge/GitHub-siddhisharmaup85--web-black?style=flat-square&logo=github)](https://github.com/siddhisharmaup85-web)

---

<div align="center">

⭐ **If you found this project helpful, give it a star!** ⭐

*Interactive Power BI dashboard analyzing world population trends across 266 countries and regions (1960–2024). Developed as part of Prodigy InfoTech Data Science Internship — Task 01.*

</div>
