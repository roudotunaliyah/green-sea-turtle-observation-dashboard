# Global Observation Patterns of the Green Sea Turtle (Chelonia mydas)

This project analyzes global occurrence records of the Green Sea Turtle (*Chelonia mydas*) using open-access biodiversity data from GBIF. The goal is to explore distribution patterns, regional observation hotspots, and temporal trends using data analytics and spatial visualization techniques.

The final output is an interactive Tableau dashboard that integrates spatial, temporal, and categorical insights into a clean and accessible format.

---

## Project Overview

Chelonia mydas is a widely distributed marine species with significant ecological and conservation relevance.  
Using more than 69,000 global occurrence records from GBIF, this project visualizes:

- Global distribution of observations  
- Countries with the highest monitoring activity  
- Observation trends over time (2005–2025)  
- Regional hotspots within Indonesia  

Dashboard components were designed to support ecological analytics and help interpret global monitoring patterns.

---

## Interactive Dashboard

Tableau Public Link:  
https://public.tableau.com/views/tableauuuu_17639082904870/Dashboard1

---

## Repository Structure

├── data/
│   └── Chelonia_mydas_for_tableau.csv        # Cleaned dataset used in Tableau
│
├── notebooks/
│   └── data_cleaning.ipynb                   # Python notebook for cleaning and wrangling
│
├── images/
│   ├── dashboard_full.png                    # Screenshot of the final dashboard
│   ├── global_map.png                        # Global distribution map
│   └── indonesia_hotspot.png                 # Indonesia hotspot visualization
│
└── README.md


---

## Data Cleaning and Wrangling (Python)

Data preprocessing was performed using Python (pandas, openpyxl).  
Key steps included:

- Removing records with missing or invalid coordinates  
- Filtering only valid occurrence records (`PRESENT`)  
- Removing duplicate GBIF occurrence IDs  
- Dropping records with missing observation year  
- Selecting relevant analytical fields  
- Exporting cleaned dataset for Tableau  

Example of core cleaning script:

df = df.dropna(subset=["decimalLatitude", "decimalLongitude"])
df = df[(df["decimalLatitude"] != 0) & (df["decimalLongitude"] != 0)]

df = df.drop_duplicates(subset=["gbifID"])
df = df[df["occurrenceStatus"] == "PRESENT"]
df = df.dropna(subset=["year"])

df.to_csv("Chelonia_mydas_for_tableau.csv", index=False)

---

## Visualizations
The Tableau dashboard consists of four main visualization components:

1. Global Distribution Map
Shows worldwide observation points based on valid latitude and longitude coordinates.

2. Top Countries by Observation Records
Highlights countries with the highest number of recorded sightings.

3. Observation Trend Over Time
Displays temporal variation in Green Sea Turtle observations across two decades.

4. Indonesia Regional Hotspot Map
Identifies key provinces and coastal regions with the highest monitoring activity.

---

## Key Insights

Southeast Asia, particularly Indonesia and Malaysia, shows the highest concentration of observation records.
Australia and Pacific regions contribute significantly to global monitoring datasets.
Western Atlantic regions such as Brazil and Mexico also appear as strong observation hotspots.
Observation peaks around 2013–2014 likely correspond to bulk dataset uploads to GBIF.
Indonesia’s hotspots include NTT, NTB, Sulawesi, Papua, Maluku, and parts of Kalimantan Timur.

---

## Tools and Technologies

Python (pandas, openpyxl)
Tableau Public
Excel/CSV
GitHub for documentation and version control

---

## Dataset Source
GBIF.org (2025). GBIF Occurrence Download — Chelonia mydas (Linnaeus, 1758).
Open-access biodiversity dataset licensed under CC-BY.

---

## About the Author
My name is Roudotun Aliyah, a final-year Biology student transitioning into the field of Data Analytics.
My interests include environmental data, biodiversity informatics, and ecological analytics, with a focus on how data can support conservation and research.

---
