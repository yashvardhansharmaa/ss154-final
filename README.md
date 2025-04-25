# Lighting the Way: How Early Power Infrastructure Fueled the Internet Boom

## 📘 Project Overview

This project investigates whether early national electrification impacted the adoption of the internet in the late 20th century. We apply a **Difference-in-Differences (DiD)** framework using cross-country panel data from 1990–2005. Our analysis focuses on whether achieving widespread electrification before 1950 helped certain countries adopt the internet faster once it became globally available.

---

## 📊 Methodology

- **Causal Strategy**:  
  We use a Difference-in-Differences design with:
  - **Treatment Group**: Countries with national electrification coverage before 1950.
  - **Control Group**: Countries electrified after 1950.
  - **Outcome Variable**: Internet users per 100 people.
  - **Periodization**: Pre-internet (pre-1995), early internet (1995–1999), and mature internet (post-2000).
  
- **Controls**:  
  Chosen based on DAG analysis and confounding pathways:
  - GDP per capita
  - Secondary education rates
  - Urbanization levels
  - Telecom infrastructure (landlines, mobile subscriptions, etc.)
  - Telecom Infrastructure Index (constructed variable)

- **Data Sources**:
  - [Historical Cross-Country Technology Adoption (Comin & Hobijn, 2010)](https://www.nber.org/research/data/historical-cross-country-technology-adoption-hccta-dataset)
  - World Bank Development Indicators (1990–2003)

---

## 📦 Dependencies

Install the required R packages before running the notebook:

```r
packages <- c(
  "dplyr", "magrittr", "ggplot2", "tidyr", "fixest", 
  "sandwich", "lmtest", "clubSandwich", "stargazer", 
  "tibble", "broom", "stringr"
)
missing <- packages[!packages %in% installed.packages()[,"Package"]]
if(length(missing)) install.packages(missing, dependencies = TRUE)
lapply(packages, library, character.only = TRUE)
