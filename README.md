# NZ Vehicle Theft Analysis (2021–2022)

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
