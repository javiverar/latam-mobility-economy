# Urban Mobility vs. Economic Productivity in Latin American Cities (2024)

Does traffic congestion relate to economic productivity? This project combines **TomTom Traffic Index** data (1M+ records) with **OECD city indicators** to find out, and to suggest where transport infrastructure investment should be prioritised.

## Key findings

- **No relationship between GDP per capita and congestion**: correlation of 0.06 with the traffic index and 0.28 with total jam delay.
- **City size explains congestion**: population correlates 0.88 with total jam delay and 0.65 with the traffic index.
- **"Most congested city" depends on the metric**: by total delay, Mexico City leads; by delay per 10 km (normalised), Manila, Istanbul and Bucharest lead.
- **Priority candidate: Bogotá** — highest traffic index in the sample (37.6), GDP per capita below the median and 10% unemployment.
- **Data quality issues flagged**: Santiago de Chile shows an implausible GDP per capita (2,277 USD), and some cities have negative delay values.

## Contents

- `latam_mobility_economy_2024.ipynb` — full analysis: cleaning, aggregation, merge, visualisation, correlations and executive summary (in Spanish).

## Open in Colab

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/javiverar/latam-mobility-economy/blob/main/latam_mobility_economy_2024.ipynb)
## Methodology

1. **Cleaning**: date columns converted to datetime; numeric columns stored as text in European format (thousand separators, decimal commas, `%` signs) converted to float; columns renamed to snake_case.
2. **Filtering**: 2024 only (traffic data covers October–December 2024).
3. **Aggregation**: traffic records averaged per city and year (886,779 → 387 rows).
4. **Integration**: inner join with OECD data on city and year → 15 cities, 7 countries, no duplicates or missing values.
5. **Analysis**: boxplots and histograms for distributions and outliers; correlation matrix between mobility and economic variables.

## Limitations

- Small sample: 15 cities, 8 of them in Brazil.
- Traffic data covers one quarter, not a full year.
- Correlation does not imply causation.

## Reproducibility

The notebook reads the data from the TripleTen platform (`/datasets/tomtom_traffic.csv`, `/datasets/oecd_city_economy.csv`). To run it elsewhere, replace those paths with local copies of the datasets.

## Tools

Python · pandas · NumPy · Matplotlib · Seaborn

---
Project completed as part of the TripleTen Data Analytics bootcamp.
