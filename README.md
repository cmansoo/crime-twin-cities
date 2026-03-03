# Crime + Weather Data Integration (Twin Cities / Minneapolis)

This project builds an analysis-ready dataset by **cleaning and combining Minneapolis crime incident records (2017–2023)** across years with **geospatial layers** and **weather data**. The main focus is **data engineering + feature creation** to set up future modeling/visualization work.

> Current notebook focuses on **Minneapolis** (2017–2023). :contentReference[oaicite:0]{index=0}

---

## Project Objectives
- Standardize annual crime files that have **inconsistent schemas** across years (2017–2018 vs 2019–2023). :contentReference[oaicite:1]{index=1}  
- Fix data quality issues (e.g., datetime formatting differences in 2018). :contentReference[oaicite:2]{index=2}  
- Combine disparate sources (crime incidents + geospatial + weather) into a single dataset and create features for downstream analysis. :contentReference[oaicite:3]{index=3}

---

## Data Sources
The notebook uses the following sources: :contentReference[oaicite:4]{index=4}  
1. **Minneapolis Police Incidents** (Open Data Portal)  
2. **NOAA Local Climatological Data (LCD)** for weather  
3. **Hennepin County Police Stations** (ArcGIS Hub)

(Links are listed in the notebook.) :contentReference[oaicite:5]{index=5}

---

## What the Notebook Does
High-level pipeline (as implemented in `process_data_mpls.ipynb`):

1) **Load yearly incident files (2017–2023)** and normalize column names/structures :contentReference[oaicite:6]{index=6}  
2) **Clean and standardize timestamps** (notably 2018 formatting) :contentReference[oaicite:7]{index=7}  
3) **Assess data quality** and resolve cross-year inconsistencies :contentReference[oaicite:8]{index=8}  
4) **Scrape/ingest weather data** (LCD) for potential crime–weather analyses :contentReference[oaicite:9]{index=9}  
5) **Feature creation** to support future analysis :contentReference[oaicite:10]{index=10}  
6) **Load yearly geospatial crime files** (GeoJSON) and combine for mapping/spatial joins :contentReference[oaicite:11]{index=11}  

---

## Unified Schema (Target Columns)
After harmonizing across years, the notebook aims to produce a consistent structure including: :contentReference[oaicite:12]{index=12}  
- case number (unique ID)  
- public address  
- reported datetime / begin datetime  
- latitude / longitude  
- precinct  
- neighborhood  
- offense code + description  

---

## Repository Contents
- `process_data_mpls.ipynb` — main data processing + integration notebook :contentReference[oaicite:13]{index=13}  
- `README.md` — project overview (this file)

> Note: The repository may reference local `data/` paths in the notebook; raw data files are typically not committed to GitHub. :contentReference[oaicite:14]{index=14}

---

## Future Work Ideas
- Build neighborhood-level time series (weekly/monthly) and study trends
- Explore relationships between **weather (temperature/precipitation)** and incident volume/type
- Add St. Paul data and unify a broader **Twin Cities** dataset
- Create interactive maps and dashboards (e.g., GeoPandas/folium/kepler.gl)

---

## Author
Mansoo Cho
