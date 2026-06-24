
# Retail Allocation & Inventory Risk Analysis

## Dashboard Preview

### Executive Summary

![Executive Summary](screenshots/Page_1_Executive_Summary.png)

### Warehouse Performance Analysis

![Warehouse Performance](screenshots/Page_2_Warehouse_Performance.png)

### SKU Risk Analysis

![SKU Risk Analysis](screenshots/Page_3_SKU_Risk_Analysis.png)

### Trend Analysis

![Trend Analysis](screenshots/Page_4_Trend_Analysis.png)

---

# Project Overview

This project simulates a Retail Allocation Analyst scenario by analysing inventory performance, stock flow, warehouse coverage, product risk, and demand forecast impact across a retail network.

Using Python, Pandas, and Power BI, the project transforms raw inventory data into actionable allocation recommendations that support inventory planning, replenishment prioritisation, and business decision-making.

The analysis focuses on answering four key business questions:

* Is inventory healthy across the portfolio?
* Which products carry the highest inventory risk?
* Which warehouses perform better or worse?
* When does inventory risk occur and what actions should be taken?

---

# Business Context

Retail businesses must balance product availability with inventory efficiency.

Insufficient inventory can result in stock shortages and lost sales, while excessive inventory can increase holding costs and reduce working capital efficiency.

This project evaluates inventory health across products and warehouses and develops allocation recommendations based on inventory coverage, demand forecasts, and inventory risk exposure.

---

# Dataset

### Source

High-Dimensional Supply Chain Inventory Dataset (Kaggle)

### Dataset Size

* 91,250 records
* 50 SKUs
* 5 Warehouses
* 365 daily inventory snapshots

### Key Variables

* Inventory Level
* Units Sold
* Demand Forecast
* Warehouse ID
* SKU ID
* Supplier ID
* Region
* Reorder Point
* Order Quantity
* Promotion Flag
* Stockout Flag

---

# Analysis Framework

## Step 1 – Data Quality Validation

Performed validation checks on:

* Missing values
* Duplicate records
* Data types
* Date ranges
* Forecast anomalies

A total of 892 records contained zero demand forecasts and required special handling during coverage calculations.

---

## Step 2 – Inventory Coverage Analysis

Inventory Coverage was calculated as:

**Inventory Coverage = Inventory Level ÷ Demand Forecast**

Inventory health was classified into five categories:

| Inventory Status | Coverage Rule      |
| ---------------- | ------------------ |
| Critical         | Coverage < 14      |
| Healthy          | 14 ≤ Coverage ≤ 35 |
| High Inventory   | 35 < Coverage ≤ 90 |
| Overstock        | Coverage > 90      |
| Unknown          | Forecast = 0       |

### Inventory Health Distribution

| Status         | Percentage |
| -------------- | ---------- |
| Healthy        | 47.41%     |
| High Inventory | 29.83%     |
| Critical       | 16.77%     |
| Overstock      | 5.00%      |
| Unknown        | 0.98%      |

---

## Step 3 – Product Risk Analysis

A Critical Rate metric was developed to identify products with persistent inventory shortages.

**Critical Rate = Critical Inventory Records ÷ Total SKU Records**

Products were segmented into:

* High Risk
* Normal Risk
* Low Risk

### Risk Distribution

* High Risk Products: 5
* Normal Risk Products: 36
* Low Risk Products: 9

---

## Step 4 – Warehouse Performance Analysis

Warehouse performance was evaluated using:

* Median Inventory Coverage
* Critical Inventory Rate
* Overstock Rate
* Units Sold

### Key Findings

| Warehouse | Median Coverage |
| --------- | --------------- |
| WH_2      | 24.46           |
| WH_4      | 23.82           |
| WH_5      | 23.41           |
| WH_1      | 23.01           |
| WH_3      | 22.77           |

WH_2 demonstrated the strongest inventory performance.

WH_3 showed the highest exposure to critical inventory risk.

---

## Step 5 – Demand Forecast Impact Analysis

Monthly trends were analysed to understand how forecast demand influences inventory risk.

The relationship between:

**Forecast Demand ↑ → Inventory Coverage ↓ → Critical Inventory Risk ↑**

was evaluated across the full year.

### Key Insight

Inventory risk increased significantly during Q1–Q2 when forecast demand was highest and inventory coverage was lowest.

As demand declined through the second half of the year, inventory coverage improved and critical inventory risk decreased substantially.

---

# Dashboard Overview

## Page 1 – Executive Summary

* Inventory Health Distribution
* Allocation Action Summary
* Critical Inventory KPIs

## Page 2 – Warehouse Performance Analysis

* Warehouse Coverage Ranking
* Warehouse Critical Risk Ranking
* Warehouse Performance Summary

## Page 3 – Product Risk Analysis

* Top 10 Critical Product Ranking
* Product Risk Segment Distribution
* High Risk Product List

## Page 4 – Trend Analysis

* Monthly Critical Inventory Trend
* Monthly Coverage Trend
* Monthly Demand Forecast Trend

---

# Key Findings

### Inventory Health

* 47.4% of inventory was classified as Healthy.
* 16.8% of inventory records were identified as Critical.
* 5.0% of inventory was classified as Overstock.

### Product Risk

* Only 10% of products were classified as High Risk.
* A small group of products contributed disproportionately to inventory shortages.

### Warehouse Performance

* WH_2 demonstrated the strongest inventory performance.
* WH_3 showed the highest exposure to inventory risk.

### Demand Forecast Impact

Forecast demand was identified as the primary driver of inventory shortages.

Periods of higher forecast demand were consistently associated with lower inventory coverage and increased critical inventory exposure.

---

# Business Recommendations

### Prioritise High-Risk Products

Focus replenishment efforts on products with consistently high critical inventory rates.

### Improve Forecast Visibility

Strengthen forecasting processes during peak demand periods to reduce inventory shortages.

### Monitor Inventory Coverage

Use inventory coverage as a leading indicator for stock availability and replenishment planning.

### Maintain Current Allocation Strategy

Approximately half of all inventory was classified as healthy, indicating that current allocation practices are effective for most products.

---

# Tools Used

* Python
* Pandas
* Power BI
* Jupyter Notebook
* CSV Data Processing

---

# Repository Structure

```text
data/
├── raw_data/
│   └── supply_chain_dataset1.csv

├── processed_data/
│   ├── fact_inventory_enriched.csv
│   ├── warehouse_summary.csv
│   ├── sku_risk_summary.csv
│   ├── monthly_trend_summary.csv
│   └── action_summary.csv

screenshots/
├── Page_1_Executive_Summary.png
├── Page_2_Warehouse_Performance.png
├── Page_3_SKU_Risk_Analysis.png
└── Page_4_Trend_Analysis.png

Retail_Allocation_Inventory_Risk_Analysis.ipynb

Retail_Allocation_Inventory_Risk_Analysis.pbix

README.md
```

---

# Skills Demonstrated

* Inventory Analysis
* Stock Flow Monitoring
* Demand Forecast Analysis
* Product Segmentation
* Inventory Risk Assessment
* Allocation Decision Support
* Power BI Dashboard Development
* Data Storytelling
* Business Recommendation Development
