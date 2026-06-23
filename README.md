# NZ Vehicle Theft Analysis (2021–2022)

An exploratory data analysis of **4,538 vehicle theft records** across New Zealand, built in Microsoft Excel with an interactive HTML dashboard.

---

## Workbook Preview

### Sheet 1 – Cleaned Data
![Cleaned Data](cleaned_data.png)

### Sheet 2 – Cards
![Cards](cards.png)

### Sheet 3 – Summary Stats
![Summary Stats](summary_stats.png)

### Sheet 4 – Dashboard
![Dashboard](dashboard.png)

---

## Project Overview

This project analyzes a relational dataset of vehicle theft incidents reported to NZ Police. Three separate raw tables were cleaned, joined, and analyzed entirely in Excel to uncover patterns by region, vehicle type, brand, color, time, and vehicle age.

---

## Dataset

The raw data came as three separate relational text files that were cleaned and joined using VLOOKUP/XLOOKUP in Excel:

| Table | Columns | Description |
|---|---|---|
| `stolen_vehicles` | `vehicle_id`, `vehicle_type`, `make_id`, `model_year`, `vehicle_desc`, `color`, `date_stolen`, `location_id` | Core theft records — one row per stolen vehicle |
| `make_details` | `make_id`, `make_name`, `make_type` | Brand lookup — classifies each make as Standard or Luxury |
| `locations` | `location_id`, `region`, `country`, `population`, `density` | NZ regional data — used to map thefts to regions |

After joining all three on `make_id` and `location_id`, the unified table gained additional derived columns: `Day` (day of week), `Vehicle Age` (years at theft), and `Age Group` (0–4, 5–9, 10–14, etc.).

---

## Excel Workbook Structure

The workbook (`EXCEL PROJECT.xlsx`) has 4 sheets:

**Sheet 1 — Cleaned Data**
The unified, analysis-ready table. All three source tables were joined here using VLOOKUP/XLOOKUP. Contains all 4,538 records with 14 columns including the original fields plus derived columns (`Day`, `Vehicle Age`, `Age Group`). This is the source of truth for all pivot tables and charts.

**Sheet 2 — Cards**
Raw pivot tables and slicers powering the KPI cards. Includes breakdowns by: color of vehicle stolen, thefts by year, thefts by month, thefts by day, most stolen brand, most targeted vehicle type, region with highest theft, age group distribution, and luxury vehicle theft %. Slicers allow filtering by `color`, `vehicle_type`, `region`, `Age Group`, and `Years (date_stolen)`.

**Sheet 3 — Summary Stats**
A clean reference table consolidating all key aggregations in one place. Covers: key metrics summary, thefts by region, thefts by vehicle type, thefts by day, top brands, thefts by color, and thefts by age group. Used as a quick-reference companion to the dashboard.

**Sheet 4 — Dashboard**
The main visual output. Contains 10 KPI metric cards, a monthly theft trend line chart (combined + year-over-year comparison), thefts by region bar chart, vehicle type doughnut chart, top 12 stolen brands bar chart, thefts by vehicle color chart, thefts by day of week, and vehicle age at time of theft. Fully interactive via slicers (`Years`, `region`, `vehicle_type`, `color`).

---

## Key Insights & Summary

**Scale and growth**
Vehicle theft in New Zealand grew sharply — from 1,663 cases in 2021 to 2,875 in 2022, a **+73% year-on-year increase**. March 2022 was the single worst month with 825 cases.

**Where thefts happen**
Auckland dominates with **1,630 cases** (36% of all thefts), more than double the next highest region, Canterbury (660). Wellington (417) and Bay of Plenty (445) follow. Southland had the fewest reported thefts (26).

**What gets stolen**
Stationwagons (953), Saloons (853), and Hatchbacks (645) are the top three vehicle types — everyday passenger cars. Trailers (582) are also heavily targeted, likely due to poor security. Luxury vehicles make up only **4.2%** of thefts — thieves overwhelmingly target standard, older vehicles.

**Which brands**
Toyota leads by a wide margin at **716 cases**, followed by Trailer (543 — generic/unbranded trailers), Nissan (482), Mazda (433), and Ford (312). The dominance of Toyota and Nissan reflects their prevalence on NZ roads, not any particular vulnerability.

**Vehicle age**
The average stolen vehicle was **16.4 years old** at the time of theft. The 0–4 year age group still shows 527 cases, but the largest cohort is 10–14 year old vehicles (668 cases) and 15–19 year olds — suggesting older vehicles with fewer electronic immobilisers are the primary target.

**Color**
Silver is the most commonly stolen color (**1,272 cases**), followed by White (934) and Black (589). This likely reflects the general distribution of vehicle colors in NZ rather than thieves actively targeting specific colors.

**Timing**
Monday is the peak theft day (**749 cases**), with Sunday the slowest (560). Thefts are broadly spread across the week with no extreme outliers, suggesting opportunistic rather than highly planned theft patterns.

---

## Interactive HTML Dashboard

The file `nz_theft_dashboard.html` is a standalone interactive dashboard built on top of the Excel analysis. Open it in any browser — no internet required.

Supports filtering by:
- Year (2021 / 2022 / All)
- Region
- Make type (Standard / Luxury)
- Vehicle type

---

## Files

```
├── EXCEL PROJECT.xlsx          # Full workbook — 4 sheets (see structure above)
├── nz_theft_dashboard.html     # Standalone interactive dashboard (open in browser)
├── cleaned_data.png            # Sheet 1 — unified joined table
├── cards.png                   # Sheet 2 — pivot tables and slicers
├── summary_stats.png           # Sheet 3 — aggregated reference tables
├── dashboard.png               # Sheet 4 — visual dashboard
└── README.md
```

---

## Tools & Approach

- **Microsoft Excel** — data cleaning, VLOOKUP/XLOOKUP joins, pivot tables, charts, slicers, KPI cards, and the full dashboard
- **Claude AI** — converted the completed Excel analysis into a standalone HTML dashboard for web presentation

---

## Notes

Raw data was sourced as three separate relational text files (stolen_vehicles, make_details, locations). All data cleaning, joining, and analysis was performed manually in Excel. The HTML dashboard was generated with Claude AI as a presentation layer on top of the Excel work.# NZ Vehicle Theft Analysis (2021–2022)

An exploratory data analysis of vehicle theft incidents across New Zealand, covering the period October 2021 to April 2022.

---

## Project Overview

This project analyzes a relational dataset of **4,538 vehicle theft records** from New Zealand. The goal was to identify theft patterns by region, vehicle type, brand, color, and time — and surface actionable insights from the data.

---

## Dataset

The raw data consisted of three separate relational tables that were cleaned, joined, and analyzed:

| Table | Description |
|---|---|
| `stolen_vehicles` | Core theft records — vehicle type, make, model year, color, date stolen, location |
| `make_details` | Vehicle brand lookup — brand name and classification (Standard / Luxury) |
| `locations` | NZ regional data — region name, population, population density |

**Data cleaning performed:**
- Removed duplicate and null records
- Standardized date formats across the stolen_vehicles table
- Resolved inconsistent vehicle type labels
- Joined the three tables on `make_id` and `location_id` foreign keys to build a unified analysis table

---

## Tools Used

- **Microsoft Excel** — data cleaning, table joins (VLOOKUP/XLOOKUP), pivot tables, aggregations, and all core analysis
- **Claude AI** — used to convert the finalized Excel analysis into an interactive HTML dashboard for presentation

---

## Key Findings

- **4,538** total theft cases recorded across the dataset
- **Auckland** was the theft hotspot with **1,630 cases** — by far the highest of any region
- **Stationwagon** was the most stolen vehicle type (**953 cases**)
- **Toyota** was the most targeted brand (**716 cases**)
- **Silver** was the most common color among stolen vehicles (**1,272 cases**)
- The average stolen vehicle was **16.4 years old** at the time of theft — suggesting older vehicles with weaker security are disproportionately targeted
- **Monday** was the peak theft day (**749 cases**)
- **March** was the peak month (**825 cases**)
- Theft volume increased **+73% year-on-year** from 2021 to 2022
- Luxury vehicles made up only **4.2%** (190 cases) of total thefts — standard/everyday vehicles were the primary targets

---

## Dashboard

The interactive dashboard (`nz_theft_dashboard.html`) supports filtering by:
- Year (2021 / 2022 / All)
- Region
- Make type (Standard / Luxury)
- Vehicle type

Open the HTML file in any browser to explore the data interactively.

---

## Files

```
├── EXCEL PROJECT.xlsx          # Full analysis workbook (cleaned data + pivot tables)
├── nz_theft_dashboard.html     # Interactive dashboard (open in browser)
└── README.md                   # This file
```

---

## Notes

The raw dataset was sourced as separate relational text files. Data cleaning and all analysis was done manually in Excel. The HTML dashboard was generated with Claude AI as a visualization layer on top of the completed Excel analysis.
