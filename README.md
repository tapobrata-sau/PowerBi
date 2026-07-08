# 🚗 Road Accident Analysis Dashboard | Power BI

## 📌 Project Overview

The **Road Accident Analysis Dashboard** is an interactive Power BI report developed to analyze road accident data and identify patterns in accident severity, vehicle involvement, road characteristics, speed limits, weather conditions, and geographical distribution.

The dashboard transforms raw accident records into meaningful visual insights, enabling users to explore accident trends and supporting better road safety decision-making.

---

# 📊 Dashboard Preview

<img width="1232" height="697" alt="Screenshot 2026-07-09 043424" src="https://github.com/user-attachments/assets/09d77029-8ecc-44b1-9578-2c3bc89f3311" />
<img width="1227" height="695" alt="Screenshot 2026-07-09 043610" src="https://github.com/user-attachments/assets/a7f42b0a-cf81-4ba7-84f8-f8db56d5cb42" />


---

# 🎯 Project Objectives

This dashboard answers several important business questions:

- What is the total number of road casualties?
- How many Fatal, Serious and Slight casualties occurred?
- Which vehicle type is involved in the highest number of casualties?
- Which road type experiences the highest casualties?
- How do light conditions affect accidents?
- What speed limits are associated with more accidents?
- Where are accident hotspots located?
- How do weather conditions and road surface conditions influence accidents?

---

# 📈 Dashboard KPIs

The dashboard contains the following KPI cards:

| KPI | Description |
|------|-------------|
| Total Casualties | Total number of casualties recorded |
| Fatal Casualties | Total fatalities |
| Serious Casualties | Total serious injuries |
| Slight Casualties | Total slight injuries |
| Top Vehicle | Vehicle type with the highest casualties |

---

# 📊 Dashboard Visuals

The dashboard includes:

### 🚗 Vehicle Type Analysis
Shows total casualties by vehicle type.

Insights:
- Car contributes the highest number of casualties.
- Vans and motorcycles follow behind.

---

### 🛣 Road Type Analysis

Displays casualties by road type.

Major road types include:

- Single Carriageway
- Dual Carriageway
- Roundabout
- One-way Street
- Slip Road

---

### 💡 Light Condition Analysis

Analyzes accidents occurring under:

- Daylight
- Darkness (lights lit)
- Darkness (lights unlit)
- Darkness (no lighting)

---

### 🚦 Speed Limit Analysis

Shows accident distribution across different speed limits.

Used to identify roads with higher accident frequency.

---

### 🗺 Accident Location Map

Interactive Azure/Bing Map displaying accident locations using latitude and longitude.

Features:

- Zoom
- Pan
- Interactive filtering
- Geographic accident hotspots

---

### 🎛 Interactive Filters

Users can filter the dashboard using:

- Road Surface Conditions
- Weather Conditions

All visuals update dynamically based on selected filters.

---

# 📂 Dataset Information

The dashboard uses road accident data containing fields such as:

- Accident_Index
- Accident Date
- Number_of_Casualties
- Accident Severity
- Vehicle Type
- Road Type
- Speed Limit
- Light Conditions
- Weather Conditions
- Road Surface Conditions
- Latitude
- Longitude
- Local Authority
- Year
- Month

---

# 🧹 Data Preparation

Data preparation was completed using Power Query.

Steps included:

- Importing Excel data
- Removing duplicate records
- Handling missing values
- Correcting data types
- Creating Date table
- Standardizing category names
- Creating DAX measures
- Building interactive visuals

---

# 📐 DAX Measures Used

## Total Casualties

```DAX
Total Casualties =
SUM(Data[Number_of_Casualties])
```

## Total Fatal Casualties

```DAX
Total Fatal Casualties =
CALCULATE(
    SUM(Data[Number_of_Casualties]),
    Data[Accident_Severity]="Fatal"
)
```

## Total Serious Casualties

```DAX
Total Serious Casualties =
CALCULATE(
    SUM(Data[Number_of_Casualties]),
    Data[Accident_Severity]="Serious"
)
```

## Total Slight Casualties

```DAX
Total Slight Casualties =
CALCULATE(
    SUM(Data[Number_of_Casualties]),
    Data[Accident_Severity]="Slight"
)
```

## Total Accidents

```DAX
Total Accidents =
DISTINCTCOUNT(Data[Accident_Index])
```

## Top Vehicle

```DAX
Top Vehicle =
VAR TopVeh =
TOPN(
1,
VALUES(Data[Vehicle_Type]),
CALCULATE(SUM(Data[Number_of_Casualties])),
DESC
)

RETURN
MAXX(TopVeh,Data[Vehicle_Type])
```

---

# 📌 Key Insights

✔ Cars contribute the largest share of road casualties.

✔ Single carriageway roads experience the highest number of casualties.

✔ Most accidents occur under daylight conditions.

✔ Speed limits around 30 mph account for the highest accident frequency.

✔ Accident hotspots are concentrated in specific districts visible on the map.

✔ Dashboard filters allow dynamic comparison based on road surface and weather conditions.

---

# 📁 Project Structure

```
Road-Accident-Analysis/
│
├── README.md
├── Road Accident Analysis Dashboard.pbix
├── data/
│      road_accident_data.xlsx
│
├── images/
│      dashboard-preview.png
│
└── docs/
       project-report.pdf
```

---

# 🚀 How to Run

1. Clone the repository

```
git clone https://github.com/yourusername/Road-Accident-Analysis.git
```

2. Open the `.pbix` file using Power BI Desktop.

3. If prompted,

Transform Data

→ Data Source Settings

→ Update Excel file path

4. Refresh the dataset.

5. Explore the dashboard using slicers.

---

# 💡 Business Recommendations

Based on dashboard insights:

- Improve road safety on Single Carriageway roads.
- Increase monitoring around 30 mph zones.
- Promote awareness for Car and Motorcycle safety.
- Improve lighting in accident-prone areas.
- Prioritize infrastructure improvements in hotspot locations.
- Monitor road surface conditions during adverse weather.

---

# 🛠 Tools & Technologies

- Microsoft Power BI
- Power Query
- DAX
- Microsoft Excel
- Azure/Bing Maps
- Data Visualization

---

# 👨‍💻 Author

**Tapobrata Sau**

📧 Email: your-email@example.com

🔗 LinkedIn:
https://www.linkedin.com/in/tapobrata-sau-b684402a8/

💻 GitHub:
https://github.com/tapobrata-sau

---

# ⭐ Support

If you found this project useful, consider giving it a ⭐ on GitHub.

---

# 📜 License

This project is intended for learning, portfolio, and demonstration purposes.
Please verify the dataset license before redistributing the data.
