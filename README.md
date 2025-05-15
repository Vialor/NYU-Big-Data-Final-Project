# NYU Big Data Final Project

This project investigates whether heating complaints filed through NYC’s 311 system can be used to predict residential fires. Using a decade of housing complaint and fire incident data, we attempted to find meaningful patterns and build predictive models that estimate fire risk at the regional and temporal level.

## 🔗 Data Sources

- [Housing Maintenance Code Complaints and Problems (NYC Open Data)](https://data.cityofnewyork.us/Housing-Development/Housing-Maintenance-Code-Complaints-and-Problems/ygpa-z7cr/about_data)
- [Fire Incident Dispatch Data (NYC Open Data)](https://data.cityofnewyork.us/Public-Safety/Fire-Incident-Dispatch-Data/8m42-w767/about_data)


## 📊 Project Overview

- **Goal**: Explore the relationship between heating complaints and fire incidents to determine if complaints could serve as an early warning system for fire risk.
- **Approach**: 
  - Processed NYC Open Data on housing complaints and fire incidents
  - Grouped data by region (latitude/longitude bins) and 2-month periods
  - Created multiple visualizations to assess correlation
  - Built Logistic Regression and Random Forest classifiers to predict fire occurrence

## 📁 Repository Structure

| File | Description |
|------|-------------|
| `Big Data Final Project Presentation.pdf` | Final presentation slides |
| `Final Project Report.pdf` | Full written report of methods, findings, and conclusions |
| `Data_Exploration.ipynb` | Notebook containing some original exploration of the data|
| `final_df.csv` | Final preprocessed dataset used for modeling |
| `fire.ipynb` | Full notebook containing loading, preprocessing, visualizations, and machine learning|
| `README.md` | This file |

## 🔍 Methods

### Data Preparation

- **Complaint Data**: Filtered for heating-related complaints from November–February, 2015–2025.
- **Fire Data**: Filtered for fire incidents from January–April, 2015–2025.
- Data was spatially grouped using fixed-size latitude/longitude grid blocks, and temporally grouped into 2-month windows.

### Visualizations

- Scatter plots of complaint count vs fire count
- Quadrant bar charts comparing high/low complaint and fire regions
- Heatmaps of fire counts and model predictions

### Modeling

- **Features Used**:
  - Heating complaint count
  - Total complaint count
  - Percentage of heating complaints
  - Complaint growth rate (delta)
  - Previous complaint count
  - Borough (one-hot encoded)
- **Models**:
  - Logistic Regression
  - Random Forest Classifier
- **Evaluation Metrics**: AUC, precision, recall, confusion matrix

## ✅ Results Summary

| Model | AUC | Precision | Recall | Test Accuracy |
|-------|-----|-----------|--------|----------------|
| Logistic Regression | 0.648 | 0.661 | 0.236 | 63.0% |
| Random Forest | 0.654 | 0.614 | 0.343 | 63.5% |

- **Key Insight**: Models showed weak predictive power. Complaint counts alone are not sufficient for robust fire prediction.
- **Heatmaps**: Model predictions correlated with dense boroughs (Brooklyn, Manhattan), similar to raw fire count data.

## 💡 Future Work

- Incorporate more features (e.g., building data, demographics, prior violations)
- Expand to streaming pipeline for real-time risk assessment
- Explore deep learning or spatio-temporal models for better performance

## 👥 Team Members

- Jesse Noppe-Brandon (@jesseb16)
- Yiyang Zhou (@Vialor)
- Weijun Xu (@Weijun124)
- Mike Zaharchenko (@mike-zaharchenko17)
