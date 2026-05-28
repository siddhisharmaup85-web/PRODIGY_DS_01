# 🌍 PRODIGY_DS_01 — World Population Distribution

📊 Interactive Power BI dashboard analyzing global population trends across 266 countries and regions (1960–2024) using the World Bank Population Dataset.

This project was created as part of the **Prodigy InfoTech Data Science Internship — Task 01**.

---

# 📌 Project Overview

The objective of this project is to visualize and analyze world population distribution across countries and regions over time using interactive Power BI dashboards.

The report provides insights into:

- Population growth trends from 1960–2024
- Most populous countries in 2023
- Region-wise population contribution
- Population distribution by country groups
- Interactive filtering using slicers

---

# 🏢 Internship Details

| Field | Details |
|---|---|
| Internship | Prodigy InfoTech |
| Track | Data Science |
| Task | Task 01 — Data Visualization |
| Intern | Siddhi Sharma |
| Tool Used | Power BI Desktop |

---

# 📂 Dataset Information

### Dataset Source
World Bank — Population, total (`SP.POP.TOTL`)

🔗 https://data.worldbank.org/indicator/SP.POP.TOTL

---

# 🛠 Tools & Technologies Used

- Power BI Desktop
- Power Query
- DAX
- Interactive Slicers
- World Bank Open Dataset

---

# 📊 Dashboard Visuals

## 1️⃣ Top 10 Most Populous Countries (2023)

Horizontal bar chart displaying countries/regions with the highest population in 2023.

### Key Insights
- India became the most populous country in 2023
- Population exceeded 1.4 billion

---

## 2️⃣ Population Distribution by Group

Histogram showing countries grouped into population ranges:

- Under 10M
- 10M–50M
- 50M–100M
- 100M–500M
- Above 500M

### Key Insights
- Most countries have populations below 10 million
- Only a few countries exceed 500 million

---

## 3️⃣ World Population Growth (1960–2024)

Line chart visualizing global population growth over time.

### Key Insights
- World population crossed 8 billion in 2022
- Rapid growth observed after 1980

---

## 4️⃣ Population by Region

Region-wise population distribution using a horizontal bar chart.

### Key Insights
- South Asia and East Asia contribute the largest population share
- North America has comparatively smaller totals

---

## 5️⃣ KPI Cards

Dashboard KPI cards display:

- 🌍 Total World Population
- 🌎 Number of Countries/Regions
- 🏳 Selected Country Name

---

## 6️⃣ Interactive Year Slicer

Dynamic year range filter enabling interactive dashboard exploration.

### Features
- Real-time filtering
- Interactive visuals
- Dynamic updates across all charts

---

# ⚙️ Data Cleaning & Transformation

Data preprocessing was performed using **Power Query**.

### Steps Performed

- Removed blank/null values
- Renamed columns
- Converted data types
- Created custom population groups
- Merged region metadata
- Filtered unnecessary columns

---

# 📈 DAX Measures Used

## Total Population
```DAX
Total Population = SUM('Table'[Population])
```

## Country Count
```DAX
Country Count = DISTINCTCOUNT('Table'[Country Name])
```

---

# 🎨 Dashboard Features

✅ Interactive Visualizations  
✅ Dynamic Filtering  
✅ Professional Dashboard Design  
✅ KPI Cards  
✅ Trend Analysis  
✅ Region-wise Insights  
✅ User-friendly Interface

---

# 🔍 Key Findings

- India became the most populous country in 2023
- Global population crossed 8 billion in 2022
- Over 100 countries have populations below 10 million
- South Asia and East Asia dominate world population share
- Population growth has steadily increased since 1960

---

# 🚀 How to Run the Project

## Step 1
Clone or download this repository.

## Step 2
Open the `.pbix` file using **Power BI Desktop**.

## Step 3
Refresh the dataset if required.

## Step 4
Use slicers and visuals to interact with the dashboard.

---

# 📁 Project Structure

```bash
PRODIGY_DS_01/
│
├── PRODIGY_DS_01.pbix
├── README.md
├── screenshots/
│   ├── top10_population.png
│   ├── population_groups.png
│   ├── population_growth.png
│   ├── population_region.png
│   ├── kpi_cards.png
│   └── slicer.png
```

---

# 📚 Learning Outcomes

Through this project, I learned:

- Power BI dashboard development
- Data visualization techniques
- Power Query transformations
- DAX calculations
- Interactive report creation
- Data storytelling

---

# 🤝 Acknowledgements

- Prodigy InfoTech
- World Bank Open Data
- Microsoft Power BI

---

# 👩‍💻 Author

## Siddhi Sharma
B.Tech CSE Student | Data Science Enthusiast

---

# ⭐ Repository Description

Interactive Power BI dashboard analyzing world population trends across 266 countries and regions (1960–2024) using the World Bank dataset. Includes bar charts, histogram, KPI cards, line charts, region-wise analysis, and interactive year slicers. Developed as part of Prodigy InfoTech Data Science Internship — Task 01.
