# Urban vs. Rural Safe Drinking Water Access Dashboard (Power BI)

## Project Overview

This project is an interactive **Power BI data analysis dashboard** examining differences in safely managed drinking water use between urban and rural populations across countries and world regions from **2000–2024**.

The dashboard explores how drinking water access varies geographically, how urban and rural access has changed over time, and the size of the urban–rural gap. The project uses **Power BI, DAX measures, data aggregation, filtering, and interactive visualizations** to turn a global dataset into a set of clear analytical insights.

The underlying dataset was sourced from **Our World in Data's "Using safely managed drinking water in urban vs. rural areas" dataset**, which uses data from the **WHO/UNICEF Joint Monitoring Programme for Water Supply, Sanitation and Hygiene (JMP)**.

## Dashboard Features

- **Average Urban Access** – Average reported percentage of the urban population using safely managed drinking water
- **Average Rural Access** – Average reported percentage of the rural population using safely managed drinking water
- **Urban–Rural Safe Water Access Gap** – Average percentage-point difference between urban and rural access
- **World Region Filter** – Interactive filtering by Africa, Asia, North America, Oceania, and South America
- **Urban vs. Rural Access Over Time** – Comparison of urban and rural access trends from 2000 through 2024
- **Rural Safe Water Access by Region** – Comparison of average rural access across world regions
- **Urban vs. Rural Access by Region** – Regional comparison of urban and rural access
- **Rural Safe Water Access by Country** – Comparison of countries based on average rural access
- **Urban Safe Water Access by Country** – Comparison of countries based on average urban access
- **Urban–Rural Gap by Country** – Comparison of the difference between urban and rural access at the country level

## Key Analytical Areas

### Geographic Comparison

The dashboard compares safe drinking water access across world regions and individual countries, allowing differences in urban and rural access to be examined geographically.

### Urban vs. Rural Disparities

A central focus of the analysis is the difference between urban and rural access. The **Urban–Rural Safe Water Access Gap** measure expresses this difference in percentage points, providing a consistent metric for comparing disparities across geographic areas.

### Trends Over Time

The dashboard tracks urban and rural access from **2000 to 2024**, allowing changes in access levels and the urban–rural disparity to be examined over time.

### Interactive Analysis

The regional slicer allows users to dynamically filter the dashboard and examine how the KPIs and visualizations change for individual world regions.

## Key Insights

- **Urban access is consistently higher than rural access** across the overall dataset, with the dashboard's average measures showing a substantial difference between the two populations.
- The overall averages displayed in the dashboard show approximately **57% average urban access** compared with **31.8% average rural access**, resulting in an **urban–rural gap of approximately 25.3 percentage points**.
- **North America has the highest average rural access** among the five regions shown in the dashboard, followed by South America and Asia.
- **Africa has the lowest average rural access** among the regions shown, while Oceania also shows a substantial urban–rural difference.
- Regional comparisons show that the urban–rural gap varies considerably by geography rather than remaining consistent across regions.
- The country-level gap visualization highlights substantial differences between urban and rural access in several countries, including **Gambia, Eswatini, Lesotho, and Sri Lanka**.
- The time-series visualization shows that **both urban and rural access have generally increased over the 2000–2024 period**, while a difference between urban and rural access remains visible throughout the period.

These observations describe patterns in the dataset and are not intended to establish the causes of differences between countries or regions.

## Data Model & DAX Measures

### Data Model

The report uses a **single-table data model** containing country/entity, geographic region, year, and urban/rural drinking water measures.

Key fields include:

- `Entity` – Country or geographic entity
- `Entity_Code` – Entity identifier
- `World Region/Continent` – Geographic region used for filtering and comparison
- `Year` – Observation year from 2000–2024
- `Urban population` – Percentage of the urban population using safely managed drinking water
- `Rural population` – Percentage of the rural population using safely managed drinking water

### Key DAX Measures

The dashboard uses DAX measures to calculate average urban access, average rural access, and the percentage-point difference between the two.

#### Average Rural Access

```DAX
Average Rural Access =
AVERAGE('urban-vs-rural-safely-managed-d'[Rural population])


Average Urban Access =
AVERAGE('urban-vs-rural-safely-managed-d'[Urban population])
```
Urban-Rural Gap =
(AVERAGE('urban-vs-rural-safely-managed-d'[Urban population])) - (AVERAGE('urban-vs-rural-safely-managed-d'[Rural population]))

Calculates the percentage-point difference between average urban and rural drinking water access.

These measures respond dynamically to the **World Region/Continent** slicer, allowing the same calculations to be evaluated across the full dataset or for individual regions.

## Tech Stack & Techniques

- **Power BI** – Used for dashboard development, interactive reporting, visual design, filtering, and data exploration.
- **DAX** – Created calculated measures using `AVERAGE()` and arithmetic calculations to support KPI cards and urban–rural comparisons.
- **Data Aggregation** – Used average values to summarize urban and rural drinking water measures across countries, regions, and years.
- **Time-Series Analysis** – Compared urban and rural measures across the 2000–2024 period to examine changes over time.
- **Geographic Analysis** – Compared drinking water measures across world regions and individual countries.
- **KPI Development** – Created summary measures for average urban access, average rural access, and the urban–rural percentage-point gap.
- **Interactive Filtering** – Implemented a World Region/Continent slicer so users can explore the dashboard by geographic area.
- **Comparative Visualization** – Used bar charts and clustered column charts to compare urban and rural access across regions and countries.
- **Data Interpretation** – Translated a global dataset into concise visual summaries highlighting geographic differences, trends, and urban–rural disparities.

## Data Source

The dataset was obtained from **Our World in Data**:

**Using safely managed drinking water in urban vs. rural areas**

**Original data source:** WHO/UNICEF Joint Monitoring Programme for Water Supply, Sanitation and Hygiene (JMP) (https://ourworldindata.org/grapher/urban-vs-rural-safely-managed-drinking-water-source?)

**Time period:** 2000–2024

**Unit:** Percentage of the relevant population using safely managed drinking water

A safely managed drinking water service is defined as an improved drinking water source that is **located on premises, available when needed, and free from contamination**.

The dataset notes that where 2024 data is unavailable for a location, the closest available year between 2014 and 2023 may be shown instead.

**Dataset:** [Our World in Data – Using safely managed drinking water in urban vs. rural areas](https://ourworldindata.org/grapher/urban-vs-rural-safely-managed-drinking-water-source?utm_source=chatgpt.com)

## Purpose

This project was developed as part of a personal **data analytics portfolio** to demonstrate the ability to work with a real-world dataset, develop calculated measures, design interactive Power BI visualizations, and communicate patterns across geographic, demographic, and time-based dimensions.

The subject matter also draws on my previous exposure to **water resources and public-sector data**, while the primary focus of the project is data analysis, visualization, and communicating insights.

## Data Notes

The values represent the **share of the relevant population using safely managed drinking water**, expressed as percentages rather than population counts.

The underlying indicator reflects reported use of safely managed drinking water services. Our World in Data notes that the term "using" is preferred because the underlying data measures service use rather than simply whether infrastructure exists.

Data is provided by the **WHO/UNICEF Joint Monitoring Programme for Water Supply, Sanitation and Hygiene (JMP)** and published by Our World in Data.
