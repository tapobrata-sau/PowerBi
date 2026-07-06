** **Road Accident Analysis Dashboard | Power BI****



## Overview

This project is an interactive **Power BI Road Accident Analysis Dashboard** built to analyze road accident and casualty data. It converts raw data into actionable insights on accident severity, road conditions, location, vehicle type, area type, and light conditions.

The dashboard supports data-driven road-safety planning by helping users identify high-risk areas, trends, and contributing factors.

---

## Dashboard Preview

> Add a dashboard screenshot here after uploading your image to GitHub.

<img width="719" height="399" alt="image" src="https://github.com/user-attachments/assets/b2479754-ba67-42af-9022-ee86330400a7" />

```

---

## Business Problem

Road accident datasets contain large volumes of records that are difficult to interpret in spreadsheets. This project answers important questions such as:

- How many accidents and casualties occurred in 2022?
- Did casualties increase or decrease compared with the previous year?
- Which accident severity category has the highest number of casualties?
- Which road type is most associated with casualties?
- Are casualties higher in urban or rural areas?
- Do more casualties occur during daylight or dark conditions?
- Which months show higher accident activity?
- Which locations should be prioritized for safety interventions?

---

## Key Insights

- **Total casualties in 2022:** approximately **195.7K**
- **Year-over-year change:** approximately **11.9% decrease** in casualties
- **Urban area casualties:** approximately **61.9%**
- **Daylight casualties:** approximately **73.8%**
- **Single carriageway casualties:** approximately **145K**
- Casualty patterns can be compared month-wise between **2021 and 2022**
- Severity analysis highlights **Fatal**, **Serious**, and **Slight** casualties

> Values may vary depending on the source data, data cleaning rules, filters, and refresh date.

---

## Dashboard Features

- KPI cards for Total Casualties, Total Accidents, and Accident Severity
- Year-over-Year (YoY) comparison
- Monthly casualty trend comparison for 2021 and 2022
- Casualties by Road Type
- Casualties by Vehicle Type
- Casualties by Urban vs Rural Area
- Casualties by Light Conditions
- Geographic accident hotspot analysis using map visuals
- Interactive slicers and filters

---

## Visuals Used

| Visual | Purpose |
|---|---|
| KPI Cards | Show key metrics at a glance |
| Line / Area Chart | Compare monthly casualties for 2021 and 2022 |
| Horizontal Bar Chart | Compare casualties by road type |
| Donut Charts | Show proportional distribution by area and light condition |
| Map Visual | Identify accident hotspots by location |
| Slicers | Filter the dashboard interactively |

---

## Dataset Fields

The dashboard uses fields similar to the following:

- `Accident_Index`
- `Accident Date`
- `Number_of_Casualties`
- `Accident Severity`
- `Vehicle Type`
- `Road Type`
- `Urban_or_Rural_Area`
- `Light Conditions`
- `Latitude`
- `Longitude`
- `Location`
- `Year`
- `Month`

---

## Data Preparation

The following steps were performed in Power Query / Power BI:

1. Imported the road accident dataset.
2. Checked and corrected data types.
3. Removed duplicate and invalid records.
4. Handled missing values where required.
5. Created a Date table for time intelligence.
6. Standardized categorical values such as severity, road type, and light conditions.
7. Created DAX measures for KPIs and comparisons.
8. Built visuals and added slicers for user interaction.

---

## DAX Measures

### Total Casualties

```DAX
Total Casualties =
SUM(Data[Number_of_Casualties])
```

### Total Accidents

```DAX
Total Accidents =
DISTINCTCOUNT(Data[Accident_Index])
```

### Current Year Casualties

```DAX
CY Casualties =
TOTALYTD(
    [Total Casualties],
    'Date'[Date]
)
```

### Previous Year Casualties

```DAX
PY Casualties =
CALCULATE(
    [CY Casualties],
    SAMEPERIODLASTYEAR('Date'[Date])
)
```

### Year-over-Year Change %

```DAX
YoY Change % =
DIVIDE(
    [CY Casualties] - [PY Casualties],
    [PY Casualties]
)
```

### Serious Casualties

```DAX
Serious Casualties =
CALCULATE(
    [Total Casualties],
    Data[Severity] = "Serious"
)
```

---

## Project Structure

```text
Road-Accident-Analysis-PowerBI/
│
├── README.md
├── Road Accident Analysis Dashboard.pbix
├── data/
│   └── road_accident_data.xlsx
├── images/
│   └── dashboard-preview.png
└── docs/
    └── project-report.pdf
```

---

## How to Run the Project

1. Download or clone this repository.
2. Install **Power BI Desktop**.
3. Open the `.pbix` file.
4. If prompted, update the data source path:
   - Go to **Transform Data**
   - Select **Data Source Settings**
   - Update the source file location
5. Click **Refresh**.
6. Use the report slicers to explore the dashboard.

---

## Recommendations

- Improve safety infrastructure on single carriageways.
- Focus road-safety campaigns and traffic management efforts in urban areas.
- Use monthly trend data for seasonal awareness campaigns and enforcement planning.
- Improve signage, visibility, lighting, and pedestrian safety at high-risk locations.
- Use map-based hotspots to prioritize local road-safety interventions.
- Increase awareness for private vehicle and two-wheeler safety.

---

## Tools and Technologies

- **Power BI Desktop**
- **Power Query**
- **DAX**
- **Microsoft Excel / CSV**
- **Data Visualization**

---

## Author

**Tapobrata Sau**

- GitHub: `https://github.com/tapobrata-sau
- LinkedIn: `https://www.linkedin.com/in/tapobrata-sau-b684402a8/

> 

---

## License

This project is intended for **educational and portfolio purposes**.  
Please verify the original dataset license before redistributing the data.

---

## If You Like This Project

Give this repository a ⭐ on GitHub!
