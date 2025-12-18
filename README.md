# Menstrual Cycle Regularity Analysis

## Project Overview

This project analyses an open menstrual cycle dataset to assess **cycle regularity at an individual level**.  
Instead of focusing on single cycles or raw averages the analysis quantifies **variability in cycle length** using statistical measures.

The project follows a full data analytics workflow: data cleaning, aggregation, feature engineering and visualisation.

---

## Data Source

- Open dataset from Kaggle  
- Topic: menstrual cycle tracking data  
- Granularity: **cycle-level observations**

Each row in the original dataset represents one menstrual cycle for one individual.

---

## Original Data Structure

Key fields in the raw dataset:

- `new_id` – anonymised individual identifier  
- `age` – age of the individual  
- `cycle_number` – sequential cycle number  
- `cycle_start_date`, `cycle_end_date` – cycle dates  
- `cycle_length` – length of the cycle in days  
- `conception_cycle` – indicates whether conception occurred in that cycle  

The raw data contained missing values and was not directly suitable for analysis.

---

## Data Cleaning and Preparation

The following steps were performed:

- Removed or excluded records with missing `cycle_length`
- Converted relevant columns to numeric formats
- Ensured sufficient observations per individual for reliable statistics
- Prepared a cleaned cycle-level CSV for analysis

Result: a consistent dataset suitable for aggregation and statistical analysis.

---

## Aggregation and Feature Engineering

The key analytical step was **aggregating data from cycle-level to person-level**.

For each individual (`new_id`) the following metrics were calculated:

- `mean` – average cycle length  
- `std` – standard deviation of cycle length  
- `count` – number of recorded cycles  
- `cv_percent` – coefficient of variation (CV) in percent  

Formula used:

CV (%) = (standard deviation / mean) × 100


The aggregated results are stored in:

- `regularity_by_person.csv`

---

## Analytical Focus

The analysis focuses on **cycle regularity** not diagnosis or prediction.

- Low CV → more stable, regular cycles  
- High CV → higher variability, irregular cycles  

Using the coefficient of variation allows comparison between individuals regardless of absolute cycle length.

---

## Visualisation and Dashboard

In the Jupyter notebook (`menstrual_cycle_dashboard.ipynb`):

- Distributions of cycle length were visualised
- Person-level regularity metrics were explored
- Variability patterns across individuals were examined

The dashboard uses aggregated data rather than raw observations to avoid misleading interpretations.

---

## Key Takeaway

This project demonstrates how raw health-related time series data can be transformed into meaningful, interpretable metrics.  
By focusing on variability and stability the analysis provides a more robust view than single-cycle averages.

---

## Tools and Technologies

- Python  
- Pandas  
- NumPy  
- Matplotlib / Seaborn  
- Jupyter Notebook  

---

## Disclaimer

This project is for **educational and analytical purposes only**.  
It does not provide medical advice or clinical conclusions.

