# 🌫️ India Air Quality Analysis — Power BI
Air quality analysis across 30 Indian states and 260 cities using real government data from data.gov.in — built with Power BI

## 📌 Objective
Analyzed real-time air quality data across India to identify the most 
polluted states, cities and monitoring stations, and to compare 
pollutant levels and their geographic distribution across 30 states.

## 📂 Dataset
- **Source:** data.gov.in — Central Pollution Control Board (CPCB)
- **Records:** 3,394 station-level pollution readings
- **Coverage:** 30 States | 260 Cities | 504 Monitoring Stations
- **Pollutants:** PM10, PM2.5, NO2, SO2, CO, OZONE, NH3
- **Tools Used:** Power BI, DAX

### Page 1 — Pollution Overview
- Total States: 30 | Cities Monitored: 260 | Total Stations: 504
- Average Pollutant Level: 70.64 µg/m³
- Interactive bubble map — station level pollution across India
- Top 6 most polluted states by average pollutant level
- Top 6 most polluted cities by average pollutant level
- Average pollutant comparison across all 7 pollutant types

### Page 2 — Pollution Deep Dive
- Avg PM2.5: 74.17 µg/m³ | Avg PM10: 92.42 µg/m³ | Avg NO2: 24.45 µg/m³
- Max Pollutant Recorded: 500 µg/m³
- Top 6 most polluted monitoring stations
- Avg vs Max pollutant comparison by pollutant type
- 10 Cleanest Cities in India table

## 🧮 DAX Measures

```dax
-- Distinct count measures
Cities Monitored = DISTINCTCOUNT('AQI DATASET'[city])
Stations Monitored = DISTINCTCOUNT('AQI DATASET'[station])

-- Pollutant specific averages
Avg PM2.5 = 
CALCULATE(
    AVERAGE('AQI DATASET'[pollutant_avg]),
    'AQI DATASET'[pollutant_id] = "PM2.5"
)

Avg PM10 = 
CALCULATE(
    AVERAGE('AQI DATASET'[pollutant_avg]),
    'AQI DATASET'[pollutant_id] = "PM10"
)

Avg NO2 = 
CALCULATE(
    AVERAGE('AQI DATASET'[pollutant_avg]),
    'AQI DATASET'[pollutant_id] = "NO2"
)
```

## 🔍 Key Insights
- **PM10 and PM2.5 are the most dangerous pollutants** nationally 
  with averages of 180.06 and 169.06 µg/m³ respectively — both 
  far exceeding WHO safe limits
- **Delhi is the most polluted state** with an average pollutant 
  level of 72 µg/m³
- **Khora (UP) is the most polluted city** at 123 µg/m³ average — 
  significantly higher than the national average of 70.64
- **MIET College, Meerut recorded the highest station level 
  pollution** at 156.40 µg/m³
- **PM10 and PM2.5 hit maximum recorded levels of 500 µg/m³** — 
  20x the WHO recommended safe limit of 25 µg/m³ for PM2.5
- **Samastipur, Bihar is the cleanest city** with an average 
  pollutant level of just 7.00 µg/m³
- **NH3 is the least concerning pollutant** nationally at 
  8.85 µg/m³ average
- **North India dominates pollution concentration** as visible 
  in the geographic bubble map

## 🛠️ Tools
- Power BI — dashboard and visualizations
- DAX — calculated measures
- Data Source — data.gov.in (Government of India open data portal)
