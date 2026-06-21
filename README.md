# Amazon Europe Market Performance Analysis

A 90-day market performance analysis for a European health and wellness 
brand selling supplements across five Amazon markets (Germany, Spain, 
France, Italy, United Kingdom).

**[View the live interactive dashboard →](https://app.powerbi.com/view?r=eyJrIjoiZDIwZTk1MTEtMjY5Ni00YTVmLWIwZWEtYzdhNDVlMDU5MzI0IiwidCI6ImIyODY1ZDFhLTcwMDktNDZiOC1hYTRhLWMyMzMzMWQ3NjQ2MSJ9)**
**[View the portfolio write-up →]([your-netlify-link-here](https://bimbo-oyeyele.netlify.app/)**

> Note: The underlying dataset belongs to the analysed business and is 
> not published here. This repository contains the analysis code, 
> methodology, and aggregate findings only.

---

## Overview

This project evaluates performance across five European Amazon markets, 
with a focused 90-day deep dive into one market (Spain) against six 
revenue and efficiency targets, using 13,323 rows of daily sales and 
advertising data spanning October 2020 to April 2021.

**The core finding:** Spain missed its €550,000 revenue target by 
€44,926 — not because of weak products or a struggling market, but 
because only 29% of a €100,000 advertising budget was deployed.

---

## Methodology

### 1. Data Cleaning (Python / Pandas)
- Loaded and inspected 13,323 rows of raw daily sales and advertising data
- Checked for missing values, duplicate rows, and inconsistent data types
- Standardised date formats and currency fields
- Validated PPC cost, PPC sales, and order columns against raw totals
- Calculated derived fields: Net Profit, Net Margin, ROAS, ACoS, TACoS, 
  Organic Orders, Organic %

### 2. Exploratory Data Analysis (Python)
- Aggregated daily data into monthly summaries per market for the 
  Monthly Performance comparison
- Identified the exact 90-day window (27 Jan – 27 Apr 2021) based on 
  the most recent available data for the Spain deep dive
- Built product-level (ASIN) profitability summaries across all five 
  markets to identify top and bottom performers
- Cross-checked all percentage and currency figures against raw 
  aggregates before using them in any dashboard or narrative

### 3. Root Cause Investigation
- Compared Spain's actual ad spend (€29,239) against its allocated 
  budget (€100,000)
- Calculated the exact additional spend required to close the revenue 
  gap, using Spain's proven ROAS (3.92x)
- Analysed ROAS at the individual product (ASIN) level to identify 
  which products were over- or under-invested relative to their 
  advertising efficiency
- Compared net margin against net profit at the product level to test 
  whether high margin alone signals commercial strength

### 4. Dashboard Build (Power BI / DAX)
- Built four interactive report pages: ES Market vs Targets, Monthly 
  Performance (all markets), Product Profitability Analysis, and ES 
  Advertising Analysis
- Wrote custom DAX measures for Revenue Gap, Projected Revenue, ROAS, 
  TACoS, and Target Achievement status
- Built an interactive **What-If parameter** allowing the ad spend 
  scenario to be adjusted on a 0.001% increment slider, with all 
  visuals and KPI cards responding dynamically
- Applied conditional formatting so the dashboard visually flips from 
  "below target" to "target achieved" as the scenario changes

---

## Key Findings

1. Spain deployed only 29% of its €100,000 ad budget — the unspent 
   €70,761 was larger than the €44,926 revenue gap it needed to close
2. An additional €11,449 in ad spend, at Spain's proven 3.92x ROAS, 
   would have closed the gap entirely
3. Germany led all markets in revenue and profit; France remained the 
   weakest market despite having the same number of active products as Spain
4. France's top product had the highest net margin (32.1%) but the 
   lowest absolute profit, showing margin alone doesn't equal strength
5. Three products (UK, Italy, France) were generating negative net 
   profit and required immediate review

---

## Tools Used

`Python` · `Pandas` · `Power BI` · `DAX` · `Excel` · `Google Sheets` · `GitHub`

---

## Files in This Repository

- `notebook/` — Jupyter notebook with data cleaning, EDA, and analysis 
  code (raw dataset not included due to confidentiality)
- `dashboard-screenshots/` — static images of all four dashboard pages
