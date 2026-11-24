# Nation Clustering

Clustering countries by socioeconomic indicators from the World Bank WDI (2015), and checking how the clusters line up with World Bank income groups.

## Overview

- **Data:** 11 WDI indicators (GDP per capita, GDP growth, inflation, unemployment, trade, capital formation, life expectancy, urban population, internet users, electricity access, secondary enrollment) for 217 countries.
- **Preprocessing:** log-transform of GDP per capita, median imputation, standardization.
- **Analysis:** EDA and correlations, PCA (7 components keep ~92% of the variance), K-means and hierarchical (Ward) clustering.

## Key Findings

- K-means with k = 2 (best silhouette score) splits countries into a higher-development group (145) and a lower-development group (72).
- The clusters match income groups well: ~93% of the first are High/Upper-middle income, ~86% of the second are Low/Lower-middle income.
- Hierarchical clustering agrees with K-means on most countries and differs on 28.
- Outliers like North Korea (many missing values) and Guyana (indicators from 2015 vs current income label) show where the clusters and labels diverge.

## Files

- `Socioeconomic_Clustering.ipynb`: full analysis
- `WDICSV.csv`: from WDI bulk download (not included, get it from the [World Bank](https://datatopics.worldbank.org/world-development-indicators/))
