# Water Infrastructure and Societal Challenges Through the Lens of Data Science

A data science exploration of global water infrastructure, urbanization, and 
development indicators, with a particular focus on what aggregate datasets 
reveal — and obscure — about countries like Bulgaria.

## Overview

This project integrates four major global datasets to examine the relationship 
between water infrastructure, tourism development, urbanization, and access 
to safe drinking water across 200 countries. The analysis moves through the 
full data science pipeline: multi-source data wrangling and schema alignment, 
exploratory analysis, dimensionality reduction, clustering, and predictive 
modeling — questioning along the way whether commonly used development 
indicators accurately reflect infrastructural reality.

## Data Sources

- **FAO Aquastat** — 134 water infrastructure indicators across 200 countries 
  (2018–2020), restructured from long to wide format
- **World Bank Travel & Tourism Development Index (TTDI)** — transport and 
  connectivity metrics including air, rail, road, and seaport infrastructure
- **World Bank World Development Indicators (WDI)** — urban population, 
  displaced persons, and GDP per capita
- **EC Physical Exposure to Droughts** — environmental vulnerability indicators

## Technologies

- Python 3.x
- pandas, NumPy — data wrangling and manipulation
- scikit-learn — PCA, KMeans clustering, Linear Regression, Random Forest, 
  GridSearchCV
- SciPy — statistical correlation (Pearson and Spearman)
- Matplotlib, Seaborn — visualization

## Project Structure
```
notebooks/   - main Jupyter notebook (full pipeline)
data/        - raw datasets organized by source
```

## Data

The `data.zip` archive contains all datasets used in the analysis. Extract it 
to the project root before running the notebook. The folder structure expected 
by the notebook is preserved in the archive.

## What the Notebook Covers

- Multi-source data loading, schema inspection, and harmonization across 
  datasets with inconsistent column naming and temporal coverage
- Aquastat reshaping from long to wide format (134 indicators per country-year)
- Year alignment across sources (tourism 2021 mapped to 2020)
- Data quality audit (90%+ of Aquastat values are estimates or imputations)
- Exploratory analysis: completeness, temporal variation, country-level coverage
- PCA on water infrastructure indicators (32 high-coverage variables) to 
  extract latent infrastructure profiles
- KMeans clustering (k=4) of countries by infrastructure and tourism features
- Three regression experiments:
  - Model 1: predicting water access from PCA components + controls (R² = 0.319)
  - Model 2: predicting infrastructure development from tourism indicators (R² = 0.643)
  - Simplified models using top 5 features — Linear Regression vs Random Forest

## Key Findings

Urban population and drought exposure consistently emerge as stronger predictors 
of water access than tourism metrics. Infrastructure development is moderately 
explained by urbanization and connectivity indicators. The simplified Random 
Forest outperforms linear regression (R² = 0.266 vs 0.095), but both show 
signs of overfitting, reflecting the inherent complexity of cross-country 
infrastructure modeling.

## Notes

Final exam project for the Data Science course at SoftUni.
