# Power BI Reports

A small collection of Power BI projects built from raw CSV extracts, saved in the
[PBIP](https://learn.microsoft.com/power-bi/developer/projects/projects-overview) (Power BI Project) format so the
model, report pages, and measures are plain text and diff-able in Git.

Each project has its own folder with a `.pbip` entry point plus a `.Report` and `.SemanticModel` sub-folder — open
the `.pbip` file in Power BI Desktop to load it.

📄 **[tech-doc.html](tech-doc.html)** — full technical write-up for both projects: sources, Power Query
transformations, DAX measures, data model & join keys, and an annotated walkthrough of every report visual.
Download it and open in a browser (or view raw and save) to read the formatted version.

## Projects

### 1. Air Flights Analytics
`2024 Week 1 - Prep Air's Flow Card/`

Purchase-level flight report for Prep Air, covering one week of bookings (3,778 purchases, $4.13M revenue).
Star-schema model — one fact table, five dimensions — surfacing revenue and basket mix by class, meal type,
route, and time.

- Source: `PD 2024 Wk 1 Input.csv`
- Report: `Prep Air's Flow.pbip`

### 2. Staff Income Tax
`2024 Week 6 - Staff Income Tax/`

Workforce income-tax report covering 999 employees and £14.99M of tax paid across 20% / 40% / 45% UK-style
bands. A monthly salary fact table joins a staff master and a month calendar; a calculated aggregate table
pre-computes each employee's annual salary and banded tax. Two report pages: a workforce overview and a
per-employee running-total view showing when in the year an individual crosses each tax threshold.

- Sources: `PD 2024 Wk 6 Input.csv`, `dim_staff.csv`
- Report: `Week 6 - Staff Income Tax.pbip`

## Shared assets

- `Clear Data Analytics.json` — custom Power BI theme (Calibri, navy/grey palette) used by the Air Flights
  report.

## Tech stack

- Power BI Desktop, PBIP project format (report + semantic model as TMDL/JSON)
- Power Query (M) for ingestion and shaping
- DAX for calculated columns and measures (tax banding, running totals)

## Opening a report

1. Install [Power BI Desktop](https://powerbi.microsoft.com/desktop/).
2. Open the `.pbip` file inside either project folder.
3. Power BI Desktop will load the semantic model and report pages from their `.SemanticModel` / `.Report`
   sub-folders.
