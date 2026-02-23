# Malaysia House Price Market Analysis Dashboard (Power BI)

A Power BI dashboard that analyzes Malaysia’s residential property listings using a dataset I **web-scraped myself** from **iProperty** using **Python Scrapy**. The project focuses on **market segmentation (Low / Medium / High)**, location-based pricing, and property-type price comparisons to support data-driven insights for buyers, analysts, and researchers.

---

## Dashboard Preview

**Title:** *Malaysia House Price Market Analysis Dashboard*
Key highlights shown in the dashboard:

* **Total Listings:** ~**51.23K**
* **Price Segment Thresholds (RM):**

  * **Low:** < **490,000**
  * **Medium:** < **660,000**
  * **High:** ≥ **900,000** (others beyond Low/Medium)

---

## Project Objectives

This project aims to:

1. **Segment the Malaysia housing market** into Low / Medium / High price ranges.
2. Analyze **median house price** by:

   * **Location**
   * **Property type**
3. Provide an interactive dashboard for exploring:

   * Which locations have higher median prices
   * Which property types are generally more expensive
   * How listings are distributed across price segments

---

## Data Source (Web Scraping)

### Website

* **iProperty** (Malaysia property listing platform)

### Scraping Tool

* **Python Scrapy**
* Data collected includes common listing attributes such as:

  * Listing title / house name
  * Location (state/city/area)
  * Property type
  * Price
  * Bedrooms / bathrooms
  * Built-up / land size (if available)
  * Carpark
  * Furnishing (if available)

---

## Data Preparation & Cleaning

After scraping, the raw dataset required cleaning to make it analysis-ready.

### 1) Handling Missing Values (Null Carpark)

Many listings had missing values in **Carpark**.
To reduce bias from missing data, I filled nulls using the **median carpark value** (robust against outliers).

**Approach**

* Compute median of Carpark (excluding nulls)
* Replace null Carpark with the median

### 2) Separating House Name and Location

Some listings contained mixed text (e.g., house name + location together).
I separated and standardized them into clearer fields such as:

* **HouseName** (project/house name)
* **Location** (area/city/state depending on available structure)

This improves:

* Filtering accuracy
* Location-based aggregation (median price by location)
* Cleaner visuals and slicers in Power BI

### 3) Standardizing Price

* Ensured **Price** is numeric (RM)
* Removed symbols/commas and converted text to numbers
* Enabled correct aggregation and segmentation logic

---

## Power BI Dashboard Design

![Malaysia House Price Market Analysis Dashboard](https://github.com/azlinaaaa/Malaysia-House-Price-Market-Analysis-Dashboard/blob/9fafc884470a8d3e3b9e5f69af52e56fd177d177/Malaysia%20House%20Price%20Market%20Analysis%20Dashboard.png)


### Filters / Slicers (Left Panel)

* **Location** slicer: explore specific areas
* **Property type** slicer: compare terrace, condo, apartment, etc.
* **Price segment** slicer: focus on Low / Medium / High

---

## Key Metrics (Top Cards)

The dashboard includes KPI cards for quick context:

* **Total House**: total number of listings in the filtered view
* **Low Price Threshold**
* **Medium Price Threshold**
* **High Price Threshold**

These make the segmentation logic transparent and easy to interpret.

---

## Visuals Explanation (What Each Chart Means)

### 1) Listings by Segment (Bar Chart)

Shows the **count of listings** in each segment (Low / Medium / High).
Purpose:

* Understand market composition
* Identify which segment dominates the listings

### 2) Segment Distribution (Pie Chart)

Shows the **percentage share** of each segment.
Purpose:

* Quick view of market balance
* Supports high-level storytelling in reports

### 3) Median Price by Location (Bar Chart)

Ranks locations by **median price** (not average, to reduce outlier impact).
Purpose:

* Identify premium and affordable locations
* Compare location performance fairly even with extreme values

### 4) Median Price by Type (Bar Chart)

Compares **property types** using median price.
Purpose:

* See which property categories tend to be more expensive
* Useful for buyers/investors targeting certain property types

### 5) Location–Segment Breakdown (Treemap)

A treemap that combines **location + segment** to show which areas contribute more listings per segment.
Purpose:

* Spot hotspots where “High” listings concentrate
* Compare segment dominance by location visually

---

## Price Segmentation Logic (Low / Medium / High)

The project uses threshold-based segmentation:

* **Low**: Price < **RM 490,000**
* **Medium**: Price < **RM 660,000**
* **High**: Price ≥ **RM 900,000** (or anything beyond Low/Medium)

This segmentation supports:

* Market grouping
* Easier storytelling and comparison
* Cleaner drilldowns in visuals

---

## Tools & Technologies

* **Python**

  * Scrapy (web scraping)
  * Data preprocessing (cleaning, formatting)
* **Power BI**

  * Data model + dashboard visuals
  * DAX measures/columns for segmentation & KPIs


---

## Author

**Norazlina Shariff**

---
