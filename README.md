# NYC Bike-Sharing Data Analysis

## Overview
This project analyzes bike-sharing data from Citi Bike in New York City to identify trends and insights. The primary goal is to determine whether an insurance fee should be introduced for rides exceeding 30 minutes. The analysis is structured around fetching, processing, and visualizing the data.

## Project Structure
```
├── get_raw_data.ipynb        # Notebook for data retrieval and preprocessing
├── analyze_bike_data.ipynb   # Notebook for data analysis and visualization
├── business_analysis.html    # Generated reported based on the bike dat
├── data                      # Folder containing raw and processed data
│   ├── 01raw                 # Contains the raw ZIP files and extracted CSVs
│   ├── 02cleansed            # Contains the final cleaned Parquet files
│   ├── 03results             # Contains created figures and reports
├── README.md                 # Project documentation
```

## Data Pipeline
### **Step 1: Fetching Data**
- The `get_raw_data.ipynb` notebook retrieves Citi Bike ride data from an external S3 bucket.
- It identifies the latest (or fo individuel timestamp) available ZIP file, downloads it, and extracts its contents.
- The extracted CSV is converted into a Parquet file for efficient processing.

### **Step 2: Data Processing & Analysis**
- The `analyze_bike_data.ipynb` notebook loads the Parquet data and processes it using **PySpark**.
- Key questions investigated:
  1. How many rides exceed 30 minutes?
  2. What revenue could be generated with a $0.20 fee for extended rides?
  3. How far do people typically travel? (Distance categorized into bins: 0–1 km, 2–4 km, 4–9 km, 10+ km)
- The dataset is cleaned and transformed to facilitate efficient analysis.

### **Step 3: Data Visualization**
- The analysis leverages **Matplotlib**, **Seaborn**, and **Folium** to generate:
  - Ride duration histograms
  - Distance category breakdowns
  - Heatmaps of popular biking routes

## Requirements
To run the analysis, install the necessary dependencies:
```bash
pip install pandas numpy matplotlib seaborn pyspark folium jinja2 requests selenium webdriver-manager
```

## Running the Project
1. Run `analyze_bike_data.ipynb` to perform the analysis and generate insights.
2. Review the business_analysis.html file which summarizes all key findings.

## Conclusion
This project helps answer whether an insurance fee for extended rides is financially viable and provides insights into Citi Bike usage patterns. The findings can assist policymakers and bike-sharing companies in optimizing pricing and infrastructure planning.

---
**Author:** Lukas Dech

