# Radinal_Excel_Portfolio_Fisheries
Excel-based analysis of Indonesia's fish production (2018-2022). Cleaned FAO data, added market prices, answered: top catch, overfishing risk, revenue potential. Uses XLOOKUP, SUMIFS, Pivot Tables, Dashboard. #DataAnalyst #ExcelPortfolio


# Indonesia Fisheries Analysis (2018–2022)

**Portfolio project – Excel only**  
*Author: Radinal*  
*Repository: [https://github.com/rrraadddii/indonesia-fisheries-excel-analytics]*

---

## Overview

This project analyses **Indonesia’s fish capture production** from 2018 to 2022 using public FAO data. I cleaned the raw dataset, enriched it with market prices (web‑scraped), and answered three real‑world business questions for a fisheries manager or export planner.

All work was done in **Microsoft Excel** – no external tools. The final file contains a fully interactive dashboard, revenue estimates, and an overfishing watchlist.

---

## Business Questions Answered

1. **Which fish species have the highest total catch volume?**  
   → Identifies top species for bulk export and infrastructure planning.

2. **Which species are declining year‑over‑year?**  
   → Flags potential overfishing risks to prioritise management action.

3. **Which species give the best economic value (catch × price)?**  
   → Combines volume with market price to reveal the most valuable species for revenue.

---

## Excel Skills Demonstrated

| Skill | Where used |
|-------|-------------|
| **Data cleaning** | `SUBSTITUTE` to remove brackets from species names; filtering out zero‑catch rows; `TRIM` for consistency. |
| **Lookup functions** | `XLOOKUP` to match web‑scraped prices with the main dataset. |
| **Conditional aggregation** | `SUMIFS` to calculate yearly catches per species across multiple fishing areas. |
| **Array formulas** | `UNIQUE` + `SORT` to generate top‑species lists (Excel 365). |
| **Pivot tables & charts** | Used in separate sheets for dynamic summarisation (top 5 species, revenue leaders, declining species). |
| **Data visualisation** | Bar charts for catch volume and revenue; conditional formatting for decline alerts. |
| **Dashboard design** | One‑page dashboard with key metrics and interactive slicers. |

---

## File Structure
Radinal_Excel_Portfolio_Fisheries.xlsx
│
├── ABOUT # Author info, project context, tools used
├── ORIGINAL DATA # Raw FAO data (brackets, zeros, separate years)
├── Price (WEB SCRAPPING) # Market prices per kg (USD) for top 20 species
├── Data # Cleaned & reshaped data (species names cleaned, total per row)
├── Analysis RAW # Intermediate aggregation (total catch per species)
├── Analysis # Final table with catch, prices, revenue, % change
├── Dashboard # One‑page summary (placeholder for charts)
├── Top 5 Species by Catch # Pivot table – highest volume species
├── Top 5 by Revenue # Pivot table – highest revenue species (min estimate)
└── Declining Species # Pivot table – species with % change < -30%


---

## Step‑by‑Step Workflow (as seen in the video)

### 1. Data Cleaning (`ORIGINAL DATA` → `Data`)
- Removed square brackets `[ ]` from species names using `=SUBSTITUTE()`.
- Filtered out rows where all five years (2018‑2022) were zero.
- Added a helper column `Total` (= `SUM(F2,H2,J2,L2,N2)`) to aggregate catch per row.

### 2. Species‑Level Aggregation (`Analysis RAW`)
- Extracted unique species names with `UNIQUE()` or manual copy.
- Used `SUMIFS` across the five yearly columns to get **total catch 2018‑2022** for each species.
- Sorted by total catch to see the highest‑volume species.

### 3. Price Enrichment (`Price` sheet)
- Extracted min and max price per kg from strings like `$1.45 – $1.80` using `MID()` and `FIND()`.
- Converted to price per tonne (`*1000`).
- Brought prices into the main analysis with `XLOOKUP` (match species name, return min/max price).

### 4. Revenue Calculation (`Analysis` sheet)
- Revenue (million USD) = catch (tonnes) × price per tonne ÷ 1,000,000.
- Calculated both **min** and **max** revenue to show a range.

### 5. Year‑over‑Year Decline (`Analysis` – right side)
- For the top 20 species, extracted yearly catches using `SUMIFS` on `Data`.
- Computed percentage change from 2018 to 2022: `=(catch_2022 - catch_2018)/catch_2018`.
- Flagged species with decline >30% as **overfishing candidates**.

### 6. Dashboard
- Built a separate sheet with:
  - **Top 5 species by catch** (bar chart)
  - **Top 5 by revenue** (bar chart)
  - **Declining species table** (with conditional formatting)
- Added a slicer to filter by fishing area (optional).

---

## Key Findings

- **Highest catch volume** – `Scads nei` (2.6M tonnes), `Marine fishes nei` (2.0M), `Skipjack tuna` (2.0M).  
  → These are the backbone of Indonesia’s capture fisheries.

- **Best revenue potential** – `Snappers nei`, `Groupers, seabasses nei`, and `Blue swimming crab` generate the highest economic value despite moderate catch volumes because of their high market price.

- **Declining species** – `Groupers, seabasses nei` (-79%), `Frigate tuna` (-48%), `Yellowfin tuna` (-41%).  
  → Urgent need for quota management or seasonal closures.

---

## How to Use This Repository

1. **Download** the Excel file `Indonesia Fish Production 2018-2022 Tonnes.xlsx`.
2. Open and enable **automatic calculation** (all formulas are live).
3. Explore the **Dashboard** sheet for a quick overview.
4. Go to the **Analysis** sheet to see the full data table.
5. Filter pivot tables or change price assumptions to test different scenarios.

All cells are unlocked, but please do not modify the `ORIGINAL DATA` sheet – it is the source.

---

## Future Improvements

- Connect to live FAO API for automatic updates.
- Add **Power Query** to fully automate the cleaning and reshaping.
- Build an interactive **Power BI** version with maps and time‑series sliders.

---

## Acknowledgements

- **Data source:** FAO FishStatJ (2024) – Global capture production 1950‑2022.
- **Prices:** Compiled from global seafood market reports (2025).

---

**Portfolio contact:** [https://www.linkedin.com/in/radinal-radinal-319b8972/ / radiradinal@outlook.com]  
*Feel free to connect – I’m looking for my first data analyst role.*
