# ✈️ Flight Delay Root Cause Analysis: End-to-End Data Workflow (Excel/Sheets & Tableau)

## 📌 Executive Summary

This project is a critical case study in **Operational Performance**, aiming to perform **Root Cause Analysis (RCA)** on historical flight delay data. As a Data Analyst, I applied an **end-to-end data workflow**, from **Data Cleansing** and **Feature Engineering** in **Microsoft Excel/Google Sheets** to operational **insights visualization** in **Tableau Desktop**. The resulting **dashboard** provides actionable insights for the Operations team to improve **On-Time Performance (OTP)**.

---

## 🛠️ Tools & Data

* **Data Engineering & Cleansing:** Microsoft Excel / Google Sheets  
* **Visualization & Dashboarding:** Tableau Desktop  
* **Data Source:** Flight delay causes (`Airline_Delay_Cause.csv`)  

---

## ⚙️ Phase 1: Data Engineering & Feature Engineering (Excel/Sheets)

This phase cleanses data and creates **calculated fields** essential for in-depth analysis.

| Level | Task | Key Excel/Sheets Formula | Functional Description |
| :--- | :--- | :--- | :--- |
| **Basic** | **Text Cleaning** | `=TRIM(A2)` | Removes extra spaces in text columns (`airport_name`, `carrier_name`) to ensure **data integrity**. |
| **Basic** | **Total Delay Time** | `=SUM(I2:M2)` | Computes total delay per row (in minutes) across all delay cause columns (I2:M2). |
| **Intermediate** | **Date Extraction** | `=DATE(A2, B2, 1)` | Combines `year` (A2) and `month` (B2) into a uniform monthly date column for **Time Series Analysis**. |
| **Intermediate** | **Contribution Percentage** | `=J2/$N2` | Calculates each cause’s percentage of **Total Delay Time** (`carrier_delay` / N2) for *share of blame* analysis. |
| **Advanced** | **Risk Classification** | `=IF(N2>100000, "High Risk", "Normal")` | Categorizes operational risk using thresholds to flag airports/carriers with excessive delay minutes. |
| **Advanced** | **Unique Count Check** | `=COUNTA(UNIQUE(E:E))` | Confirms number of unique entities (airlines or airports) after cleansing (Excel 365/Google Sheets only). |

---

## 📊 Phase 2: Key Analysis & Visualization (Pivot Tables & Tableau)

### 2.1 Pivot Table Analysis (Excel/Sheets)

* **Main KPIs:** Average **Total Delay Time** and **Total Flight Volume**  
* **Dominant Root Causes:** Use `Delay Cause` as **Column Label** and SUM of `Total Delay Time` as **Value** to identify bottlenecks  
* **Operational Hotspots:** Identify **Top 10 Airports** and **Airlines** with highest delays using Value Filters  

### 2.2 Tableau Visualization (Calculated Fields)

Visualizations are designed to communicate operational insights clearly and interactively.

| Visualization | Chart Type / Method | Calculated Field | Key Operational Insight |
| :--- | :--- | :--- | :--- |
| **Delay Hotspot Map** | Geo-Spatial Map | N/A (using geographic fields `city` and `state`) | Shows airports/states with highest **Total Delay Time**, focusing geographic intervention. |
| **Cause Contribution** | Stacked Bar Chart | `[Internal Delay] = [carrier_delay]`<br>`[External Delay] = [weather_delay] + [nas_delay]` | Compares **Internal** vs **External** causes visually (*share of blame*). |
| **Seasonal Trends** | Line Chart | `DATETRUNC('month', [Date])` | Tracks monthly performance changes, supporting **forecasting** and buffer time planning for peak season. |
| **Performance Comparison** | Bar Chart (Top N Filter) | `RANK(SUM([Total Delay Time]))` | Identifies airline outliers with worst delays compared to peers. |

---

## 💡 Key Insights & Strategic Recommendations

This analysis produced actionable insights for improving **Operations Performance**:

1. **Internal vs External Issues:** Determine if delays are primarily due to **Internal Operations** (Carrier Delay) or **External Factors** (NAS/Weather Delay).  
2. **Risk Mitigation:** Use seasonal trends and **Weather Delay** data to recommend strategic **Buffer Time** on high-risk routes/months.  
3. **Targeted Improvement:** The **Top 10 Delay Airports** should be prioritized for workflow review and **Air Traffic Control coordination** to reduce NAS Delays.
