readme = """# Nashville Infrastructure Risk & Anomaly Dashboard

An interactive geospatial dashboard analyzing 41,500+ infrastructure service requests
across Nashville's council districts in 2024.



## Overview

This project combines GIS analysis, risk scoring, and machine learning anomaly detection
to identify high-risk infrastructure zones across Nashville, Tennessee.
The goal is to help decision-makers understand where resources are needed most
and detect unusual complaint patterns before they become critical failures.

## Key Findings

- Electric & Water requests average **11.3 days** to resolve — the slowest category
- **District 21 and 17** are the highest-risk areas by combined resolution time and volume
- A major complaint spike in **Week 3 (January 2024)** affected 5+ districts simultaneously,
  consistent with Nashville cold snap and pipe burst incidents
- Streets & Roads account for **81%** of all infrastructure complaints

## Features

- Interactive choropleth-style risk map with color-coded districts
- Risk scoring model combining resolution time (60%) and complaint volume (40%)
- Isolation Forest anomaly detection identifying unusual complaint surges
- Top 5 anomaly districts highlighted with warning markers
- Popup details for each complaint point (type, district, resolution time, risk level)

## Methodology

**Risk Score**
Each council district is scored based on:
- Average resolution time (weighted 60%)
- Total complaint volume (weighted 40%)

Scores are normalized using MinMaxScaler and split into Low / Medium / High
using percentile-based thresholds (33rd and 66th percentile).

**Anomaly Detection**
Isolation Forest model trained on weekly complaint counts and average resolution times
per district. Contamination parameter set to 5%, flagging statistically unusual
district-week combinations.

## Data Sources

| Dataset | Source |
|---|---|
| 311 Service Requests 2024 | [Nashville Open Data Portal](https://data.nashville.gov) |
| Council District Boundaries | Nashville Metro GIS |

## Tech Stack

| Tool | Purpose |
|---|---|
| Python | Core analysis |
| Pandas / NumPy | Data cleaning and feature engineering |
| GeoPandas | Spatial data processing |
| Scikit-learn | Risk scoring normalization, Isolation Forest |
| Folium | Interactive map visualization |
| Google Colab | Development environment |

## Project Structure
```
nashville-infrastructure-risk/
│
├── Nashville_Utility_Infrastructure_Risk_Dashboard.ipynb
├── nashville_infrastructure_risk_anomaly.html
├── README.md
└── preview.png
```

## How to Run

1. Clone the repository
2. Upload your Nashville 311 CSV from [data.nashville.gov](https://data.nashville.gov)
3. Open the notebook in Google Colab or Jupyter
4. Run all cells in order

## Author

**Kubra Gul Ibacik**
GIS Analyst | Data Scientist
Nashville, TN
[LinkedIn](https://www.linkedin.com/in/kubrarose/) | [GitHub](https://github.com/kubragul)
"""

with open("/content/drive/MyDrive/nashville-infrastructure-risk/README.md", "w") as f:
    f.write(readme)

print("README updated!")
