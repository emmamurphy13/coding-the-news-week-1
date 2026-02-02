#REPOREUTERS

Can you tell me about how the air conditioning numbers are recorded here?

The air conditioning numbers in this repository are recorded through public records requests made by Reuters to state and federal corrections departments in the U.S. The data collection process involved the following steps:

1. **Public Records Requests**: In February 2024, Reuters submitted requests to every state and federal corrections department, asking for records that indicate the presence of air conditioning systems in housing units of adult prisons.

2. **Responses**: Out of the states contacted, 35 responded. Among these, 29 states provided records detailing the presence of air conditioning, while six states either denied the request or stated they did not possess or maintain such records.

3. **Federal Prisons**: The Bureau of Prisons, which oversees all 122 federal prisons, did not respond to the request for information regarding the presence of air conditioning in their facilities.

This data is crucial for understanding how many prisons provide cooling for inmates and the conditions they endure during rising temperatures. The collected data is likely stored in the various CSV files within the repository, particularly in the air-conditioning folder.

What coding languages were used to create this?
The README file does not specify the coding languages used to create the project. However, based on the context of the repository, it likely involves data analysis and processing, which could involve languages such as:

Python: Commonly used for data analysis, especially with libraries like Pandas and NumPy.
JavaScript: If there are any web components or visualizations.
R: Often used for statistical analysis and data visualization.
To determine the exact languages used, I can check for specific files or scripts in the repository that might indicate the programming languages employed. Would you like me to do that?

yes
Finding: This repository contains data and documentation (CSV/JSON/Markdown) but no source code files were detected — I found air_conditioning_status.csv, many other .csv files, processed_temp_logs.json, and several README.md files.
Conclusion: There are no obvious coding languages used in this repo itself (no .py, .R, .js, .ipynb, package.json, requirements.txt, etc.).

What can I find out from these github files that isn't in the story

Checking air-conditioning CSV and a few sample temperature CSVs to list columns and metadata you can find that aren't in the story.

Read [](file:///Users/emmamurphy/Desktop/NewMediaWebsite/Code/coding-the-news-week-1/prison-heat-records/air-conditioning/air_conditioning_status.csv#1-1), lines 1 to 200

Reading one sample temperature CSV from Pennsylvania to see recorded variables (timestamps, temperature, unit names).

Read [](file:///Users/emmamurphy/Desktop/NewMediaWebsite/Code/coding-the-news-week-1/prison-heat-records/indoor-temperatures/pennsylvania/benner/RTU_A1_TAC%20CEAT.csv#1-1), lines 1 to 200

Searched for regex `\.pdf`, no results

Read [](file:///Users/emmamurphy/Desktop/NewMediaWebsite/Code/coding-the-news-week-1/prison-heat-records/indoor-temperatures/README.md)

Read [](file:///Users/emmamurphy/Desktop/NewMediaWebsite/Code/coding-the-news-week-1/prison-heat-records/indoor-temperatures/pennsylvania/README.md)

## Quick summary — what the files reveal beyond the story ✅

**Finding:** The repo contains *facility‑level data and raw temperature logs* that let you do more granular analysis than the story’s high‑level narrative. Below are concrete items you can get from the files that aren’t spelled out in the published story.

---

### What you can discover from the files 🔎
- **Facility-level list and contact info**  
  - air_conditioning_status.csv has every facility name, `facility_id`, full address, city, state and zip — so you can map or geolocate individual prisons.  

- **Exact AC status per facility**  
  - `ac_status` and `ac_status_details` (values: `YES`/`NO`/`NA` and `FULL`/`PARTIAL`/`NONE`) for each prison — enables counting and filtering at facility level rather than only state summaries.

- **High-resolution temperature time series**  
  - Per-facility CSVs (e.g., `indoor-temperatures/pennsylvania/...`) show timestamps and sensor columns (`Time`, `Return`, `Supply`, etc.). Some systems log hourly or every 30 minutes — letting you compute daily maxima, durations above thresholds, diurnal cycles, and peaks by hour.

- **Variation in measurement methods and frequency**  
  - The files (and READMEs) show differences by state and system (BMS, ACPAC, SB1R56, scanned PDFs), including the exact sampling times (e.g., Texas notes about 3 p.m. daily for non‑AC areas). This lets you assess comparability and data quality.

- **AI‑extracted data and provenance for California**  
  - California’s scanned PDF pages were processed into JSON (via Gemini), and the repo contains the AI-extracted dataset (plus notes about manual cleaning). That JSON likely contains page-level extraction results and source references.

- **Metadata to join with external datasets**  
  - The `facility_id` is aligned with DHS Prison Boundaries DB (mentioned in README) — so you can join to shapefiles or county/outdoor climate data for spatial analysis.

- **Files that let you do new analyses the story didn’t show**  
  - Examples: list of top facilities by maximum internal temperature, how long each facility spent above 85°F, hourly heat profiles, comparison of supply vs return temps (HVAC performance), mapping of partial vs full AC across counties.

- **No analysis code included**  
  - Repo contains data + documentation but no analysis scripts (.py/.R/.js) — so you’d write your own code to run the above analyses.

---

> ⚡ Tip: because the data formats and sampling vary by state, it’s best to standardize timestamps and document per-state sampling frequency before aggregating.

What can I learn about the graphics from these files?

What can I learn about the graphics from these files
What the files tell you about the graphics 🔍
Types of assets
State-level release maps/tables: *_for_release.png and *.pdf in many air-conditioning/<state>/ folders.
Facility/block diagrams or maps: PNGs under somerset (A‑Block, C‑Block, etc.).
Formats & sizes
PNG and PDF (PDFs sometimes multi-page exports of agency spreadsheets). Example: CA_for_release.png is 1434×1427 px, ~388 KB.
Provenance / source
Some graphics are agency-supplied (PDF metadata shows agency author/filename), not Reuters-made. California PDFs appear to be exports of CDCR spreadsheets.
Reproducibility clues
facility_id in the CSVs and the README’s link to DHS Prison Boundaries mean you can map facilities and reproduce choropleth or point maps.
Limitations
No chart-generation code or scripts in the repo — assets are static images/PDFs, so reproducing or editing requires re-creating visuals (e.g., with Python/R/JS) or editing the images manually.
Quick suggestions — what you can do next 🔧
Preview specific state PDFs or images to see captions and legends (I can extract PDF metadata/text).
Build a map by joining air_conditioning_status.csv with DHS boundaries and reproduce visuals.
Create per‑facility charts (max temp, hours >85°F) from the temperature CSVs and replace the static images with reproducible charts.
Would you like me to (pick one):

Extract text/captions from a specific PDF (e.g., California)? ✅
List all _for_release images and PDFs with basic metadata? ✅
Start reproducing a map using facility_id + DHS boundaries? ✅
Raptor mini (Preview) • 1x