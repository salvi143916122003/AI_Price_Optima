# Air Pollution Source Attribution Using AI

## Project Overview
This project aims to identify the likely sources of air pollution using environmental data and machine learning techniques. The goal is to classify pollution sources such as vehicular, industrial, agricultural, burning, and natural sources.

---

## Dataset
The project uses a combination of datasets:

- Station spatial data (`stations_with_spatial_features.csv`)
- Weather data (`weather_data.csv`)
- Synthetic pollutant concentrations generated for modeling.

Since real-world datasets do not contain labeled pollution sources, pollutant levels were simulated and rule-based labeling was applied.

---

## Data Processing Pipeline

1. Generate synthetic pollutant concentrations
2. Combine station and spatial data
3. Apply rule-based labeling to assign pollution sources
4. Generate labeled dataset for machine learning models

---

## Pollution Source Labels

The dataset contains the following classes:

- Vehicular
- Industrial
- Agricultural
- Burning
- Natural

---

## Labeling Rules

| Condition | Source |
|----------|--------|
| NO₂ > 80 and Distance_to_Nearest_Road < 0.5 | Vehicular |
| SO₂ > 50 | Industrial |
| PM2.5 > 100 and PM10 > 150 | Agricultural |
| PM2.5 > 120 | Burning |
| Otherwise | Natural |

---

## Generated Outputs

## Week 4 – Model Training

Model Used:
Random Forest Classifier

Features:
PM2.5, PM10, NO2, CO, SO2, O3
Temperature, Humidity
Wind Speed, Wind Direction
Distance to Road, Industry, Dump Site

Evaluation Metrics:
Accuracy
Precision
Recall
F1-score

Output Files:
models/pollution_model.pkl
feature_importance.png