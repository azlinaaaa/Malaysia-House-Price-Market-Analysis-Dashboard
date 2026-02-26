# Malaysia House Price Market Analysis Dashboard (Power BI)

A comprehensive **Power BI dashboard** analyzing Malaysia’s residential property market using a dataset I web-scraped from **iProperty** with **Python Scrapy**.

This project focuses on:

* 📊 Price Segmentation (Low / Medium / High)
* 📍 Location-Based Median Pricing
* 🏘 Property Type Price Comparison
* 🧩 Location–Segment Distribution Analysis

The goal is to transform raw property listings into actionable market insights for buyers, investors, and analysts.

---

# 📌 Dashboard Overview

### 🔢 Total Listings

**Total Houses: ~51.23K listings**

---

## 💰 Price Segmentation Thresholds (RM)

| Segment   | Price Range             |
| --------- | ----------------------- |
| 🟢 Low    | < RM 490,000            |
| 🟡 Medium | RM 490,000 – RM 660,000 |
| 🔵 High   | ≥ RM 900,000            |

These thresholds are displayed directly on the dashboard for transparency and interpretability.

---

# 🎯 Project Objectives

This project aims to:

* Segment Malaysia’s housing market into Low / Medium / High categories.
* Analyze **Median House Price** by:

  * 📍 Location
  * 🏘 Property Type
* Provide an interactive dashboard to explore:

  * Which locations are premium vs affordable
  * Which property types are most expensive
  * How listings are distributed across price segments
  * Which locations dominate certain price segments

---

# 📊 Dashboard Components

## 🔎 Filters / Slicers

Users can dynamically filter the dashboard by:

* Location (e.g., Ampang, Alor Setar, Putrajaya, Kota Kinabalu, etc.)
* Property Type (Terrace, Condominium, Bungalow, Apartment, etc.)
* Price Segment (Low / Medium / High)

---

## 📌 Key KPI Cards

Top-level dashboard metrics include:

* 🏠 **Total House Listings**
* 💵 Low Price Threshold (RM 490K)
* 💵 Medium Price Threshold (RM 660K)
* 💵 High Price Threshold (RM 900K)

These KPIs make the segmentation logic clear and business-friendly.

---

## 📊 1) Listings by Segment (Bar Chart)

Shows listing counts across:

* Low
* Medium
* High

Purpose:

* Understand market composition
* Identify dominant price segments

---

## 🥧 2) Segment Distribution (Pie Chart)

Displays percentage breakdown of:

* Low
* Medium
* High

Purpose:

* Quick market balance overview
* Executive-level storytelling

---

## 📍 3) Median Price by Location (Bar Chart)

Analyzes median price across locations such as:

* Ulu Langat
* Ulu Tiram
* Putrajaya
* Ayer Keroh
* Yan
* Melaka
* Wakaf Bharu
* and more

Why Median (not average)?

* Reduces impact of extreme outliers
* Provides more realistic pricing representation

Purpose:

* Identify premium areas
* Compare affordability across locations

---

## 🏘 4) Median Price by Type (Bar Chart)

Compares property types including:

* Bungalow
* Semi-Detached
* Cluster House
* 1–4 Storey Terrace / Link
* Condominium
* Serviced Residence
* Townhouse
* Apartment

Purpose:

* Understand which property types command higher prices
* Assist buyers and investors in targeting specific categories

---

## 🧩 5) Location–Segment Breakdown (Treemap)

Visualizes how each location distributes across:

* High
* Medium
* Low

Example locations include:

* Kuching
* Kota Kinabalu
* Iskandar Puteri
* Putrajaya
* Ayer Keroh

Purpose:

* Spot “High-price hotspots”
* Compare segment dominance by area
* Understand regional market structure

---

# 🧹 Data Source & Preparation

## 🌐 Data Source

**Platform:** iProperty Malaysia
**Scraping Tool:** Python Scrapy

Collected attributes include:

* Listing Title / House Name
* Location (Area / City / State)
* Property Type
* Price
* Bedrooms
* Bathrooms
* Built-up Size
* Land Size
* Carpark
* Furnishing

---

# 🧼 Data Cleaning & Transformation

## 1️⃣ Handling Missing Values (Carpark)

Many listings had null values for Carpark.

To reduce bias:

* Calculated median Carpark value
* Replaced null values with median
* Chosen because median is robust to outliers

---

## 2️⃣ Separating House Name & Location

Some listings contained mixed text (e.g., project name + location).

I separated them into structured columns:

* `HouseName`
* `Location`

Benefits:

* More accurate filtering
* Cleaner aggregation (Median by Location)
* Better slicer usability in Power BI

---

## 3️⃣ Standardizing Price

* Removed RM symbols & commas
* Converted to numeric format
* Enabled accurate aggregation
* Enabled segmentation logic using DAX

---

# 🧮 Segmentation Logic (DAX Concept)

```
Low: Price < 490,000
Medium: 490,000 ≤ Price < 660,000
High: Price ≥ 900,000
```

Used for:

* Calculated columns
* KPI Cards
* Segment-based visuals
* Treemap breakdown

---

# 🎨 Dashboard Design

* Dark theme background
* Blue–teal accents
* Clean KPI cards
* Structured layout panels
* Business-ready storytelling visuals

Designed for:

* Analysts
* Real estate investors
* Buyers
* Market researchers

---

# 🛠 Tools & Technologies

## Python

* Scrapy (Web Scraping)
* Pandas (Data Cleaning)
* Data preprocessing

## Power BI

* Data Modeling
* DAX Measures & Calculated Columns
* Interactive Visual Design
* Market Segmentation Logic

---

# 📈 Business Impact

* Smarter property investment decisions
* Identification of premium vs affordable zones
* Clear understanding of Malaysia’s housing market structure
* Data-driven segmentation insights

