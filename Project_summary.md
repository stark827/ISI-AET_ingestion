# AET Data Ingestion & Transformation Pipeline (2015–2025)

This repository contains the implementation of a partial data ingestion pipeline for processing Actual Evapotranspiration (AET) data sourced from BHUVAN (ISRO). The project focuses on transforming a decade of monthly GeoTIFF datasets (March 2015 – March 2025) into an analysis-ready structured dataset for hydrological and agricultural applications, including the National Platform of Crop Yield Forecasting (NPCYF).

📌 Project Overview

A total of 119 GeoTIFF files were obtained from BHUVAN, each representing monthly AET values across India.

Using metadata (CRS, extent, resolution), the raster files were processed to extract AET values for a set of target locations across 20 states and their districts.

Coordinate rounding (to 2 decimals) was applied to match grid precision; duplicates were resolved using mean AET values.

A two-level matching approach—exact match first, then KDTree nearest-neighbor search—ensured accurate spatial alignment.

All monthly files were converted to CSVs and combined into a long-format dataset storing state, district, latitude, longitude, date, and AET.

The final dataset was transposed into wide format, where each row represents a month and each column represents a location.

📌 Key Outputs

Cleaned reference location file (state, district, latitude, longitude)

119 processed monthly AET CSV files

Consolidated long-format dataset (2015–2025)

Final wide-format AET matrix suitable for modelling, forecasting, and time-series analysis

📌 Applications

The processed dataset supports:

Crop water demand analysis

Moisture stress detection

Seasonal and long-term variability studies

Integration into NPCYF (National Platform of Crop Yield Forecasting)

Hydrological and environmental modelling workflows
