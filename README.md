# Socio-Economic Determinants of Child Mortality (1980-2022)

## Project Overview
This project investigates the influence of key economic and social factors on child mortality rates in developing countries over a 42-year period. Using **R** and data from **Gapminder**, the analysis performs end-to-end data wrangling, visualization, and multiple linear regression modeling to quantify the impact of GDP, fertility rates, and immunization coverage.

* **Authors:** Sonia Rawat, Chinmay Shetty
* **Language:** R (Tidyverse, Janitor, Broom)
* **Output:** [View Full HTML Report](./Child_Mortality_Analysis.html) *(Download to view interactive elements)*

## Research Question
*"How do key economic and social factors (Child Mortality Rate, GDP per Capita, Fertility Rate, Immunization Coverage) influence child mortality rates in developing countries?"*

## Key Findings
The Multiple Linear Regression model explained **77.34%** of the variance in child mortality rates ($R^2 = 0.7734$).

| Predictor | Impact (Coefficient) | Significance | Insight |
| :--- | :--- | :--- | :--- |
| **Fertility Rate** | **+19.51** | $p < 2e-16$ | Strongest predictor. A 1-unit increase in fertility rate correlates with ~19.5 more deaths per 1,000 births. |
| **Immunization (DPT)** | **-0.68** | $p < 2e-16$ | Significant negative correlation. A 1% increase in vaccination coverage reduces mortality by ~0.68 deaths per 1,000 births. |
| **GDP per Capita** | **-0.0003** | $p < 2e-16$ | Statistically significant negative correlation; higher wealth correlates with lower mortality. |

## Methodology
1.  **Data Wrangling:**
    * Merged 4 separate datasets (Child Mortality, GDP, Fertility, Immunization) using `inner_join`.
    * Transformed data from wide to long format using `pivot_longer` for time-series analysis.
    * Cleaned inconsistent units (e.g., parsing "26k" to numeric 26000) using `case_when` and string manipulation.
2.  **Visualization:**
    * Created time-series line charts and scatter plots with linear regression trend lines using `ggplot2`.
3.  **Statistical Modeling:**
    * Built a Multiple Linear Regression model (`lm`) to test significance at $\alpha = 0.05$.

## Dependencies
To run this project, you will need the following R libraries:
```r
install.packages(c("tidyverse", "readxl", "janitor", "broom", "knitr", "gapminder", "ggthemes"))
