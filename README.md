# Special Topics in Analytics — Assignment 01 (PySpark)

> **Student:** Harshal Prashant Kamble • **Course/Section:** Special Topics in Analytics — Section 006 (Fall 2025) • **Date:** 2025-10-15

## 1) Dataset
- **Chosen dataset:** NYC Yellow Taxi Trip Data (TLC Trip Record Data)
- **Source link:** https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page
- **Short description:** NYC Yellow Taxi trips with timestamps, pickup/dropoff locations, fares, distances, and vendor/rate information.

## 2) Environment / How to Run
- **Tested on:** Google Colab (recommended), with Java 11 and PySpark installed in the first cell.
- **Python:** 3.10+
- **Key libs for plotting:** matplotlib, seaborn (static plots only)
- **Run steps:**
  1. Open `Assignment01.ipynb` in Google Colab.
  2. Run the first setup cell (installs Java and PySpark; sets `JAVA_HOME`).
  3. Upload a monthly TLC parquet file when prompted (e.g., `yellow_tripdata_2025-01.parquet`).
  4. Run remaining cells. Plots are displayed inline and saved under `Assignment01/Outputs/Plots/`.

## 3) Insights (Why Chosen)
1. **Fare vs Trip Distance** — Checks fare scaling; reveals non-linear pricing and outliers (useful for pricing QA and audits).  
   *Note: Outliers were removed using 1st–99th percentile bounds plus domain caps (≤100 miles, ≤$300 fare) to focus on realistic trips.*
2. **Trip Counts by Hour × Weekday** — Shows demand peaks to inform driver/shift allocation and operations planning.
3. **Average Trip Duration by Hour** — Serves as a congestion proxy for ETA forecasting and dynamic pricing windows.

## 4) Outputs
- Plots saved to `Assignment01/Outputs/Plots/` and displayed inline in the notebook:
  - `insight1_fare_vs_distance.png` (raw data version)
  - `insight2_trip_counts_heatmap.png`
  - `insight3_avg_trip_duration.png`

**Note:** No original raw data files are included in the submission. All heavy processing is done in Spark; Pandas is used only for plotting.
