# Weather WW2 : Daily Temperature Prediction

## Project status

**Completed.** The full pipeline from raw data to linear regression has been implemented in the four notebooks below.

## Project overview

This project uses the **Weather WW2** dataset from Kaggle to build an end‑to‑end data science workflow.  
The main goal is:

> **Predict the daily average temperature using other meteorological variables and the geographic location of the weather station.**

The project is implemented in Jupyter notebooks inside this `WeatherWW2` experiment folder.

## Data sources

We use two CSV files from the Kaggle dataset:

- **`Summary of Weather.csv`**  
  Contains historical weather observations (time series), including:
  - Date of observation
  - Station identifier(s)
  - Temperature variables (e.g. min / max / mean)
  - Precipitation, pressure, wind, and other meteorological measurements

- **`Weather Station Locations.csv`**  
  Contains metadata about each weather station:
  - Station identifiers
  - Station name / description
  - Country / region (when available)
  - Latitude, longitude, elevation

These two tables are linked via the station identifier (`STA`).  
They are **merged** in the first notebook to enrich the time series with geographic information (latitude, longitude, elevation, country/station name).

## Notebooks

Run the notebooks in order. Data files are read from and written to the `00_files/` folder in this directory.

| Notebook                                        | Purpose                                                                                                                                                                                                                           |
| ----------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **`01_load_and_merge.ipynb`**                   | Load `Summary of Weather.csv` and `Weather Station Locations.csv`, inspect schemas, merge on station key (`STA`), save merged data as `00_files/03_weather_ww2_merged.csv`.                                                       |
| **`02_exploratory_data_analysis.ipynb`**        | EDA on the merged dataset: structure, missing values, distributions, temporal and spatial patterns, correlations with `MeanTemp`.                                                                                                 |
| **`03_cleaning_and_feature_engineering.ipynb`** | Clean data, add time features (year, month, day-of-year), geographic features (ELEV, Latitude, Longitude), lag features (`MeanTemp_lag1`, `MeanTemp_lag2`), export model-ready dataset as `00_files/04_weather_ww2_ml_ready.csv`. |
| **`04_linear_regression_model.ipynb`**          | Time-based train/test split, preprocessing pipeline (numeric scaling + one-hot encoding), baselines (mean, persistence), linear regression, evaluation (MSE, RMSE, R²), residual analysis and coefficient inspection.             |

## Main objectives (completed)

1. **Understand the data**
   - Inspect the structure of both CSV files
   - Identify the keys needed to join weather observations with station locations
   - Explore data quality (missing values, outliers, inconsistent types)

2. **Explore and visualize**
   - Perform basic EDA on the merged dataset
   - Visualize distributions of temperature, precipitation, pressure, etc.
   - Study temporal patterns (seasonality, trends) for selected stations
   - Examine correlations between variables and the target (daily average temperature)

3. **Clean and prepare the dataset**
   - Parse and standardize date columns
   - Handle missing values and obvious outliers
   - Convert columns to appropriate types (numeric, datetime, categorical)
   - Create a clean, merged dataset ready for modeling

4. **Feature engineering**
   - Time‑based features: year, month, day, day‑of‑year, seasonality encodings
   - Geographic features from station locations: latitude, longitude, elevation, country/region
   - Optional lag features: past temperatures for each station (e.g. previous day)
   - Select a consistent set of features as input to the model

5. **Train / test split and baselines**
   - Define the prediction **target**: daily average temperature (`MeanTemp`)
   - Split the data into training and test sets, respecting the temporal order
   - Implement simple baselines:
     - Global mean temperature
     - Persistence model (today’s temperature = yesterday’s temperature)

6. **Linear regression model**
   - Build a preprocessing pipeline:
     - Scale numeric features
     - One‑hot encode categorical features (e.g. station, country, month)
   - Train a **linear regression** model using scikit‑learn
   - Evaluate performance on the test set (MSE, RMSE, R²)
   - Compare results with the baseline models

7. **Model analysis**
   - Plot predictions vs. true temperatures over time for selected stations
   - Analyze residuals and their distribution
   - Inspect model coefficients to understand which features drive the predictions (with appropriate caution)

## Project structure

```
WeatherWW2/
├── README.md
├── 00_files/
│   ├── 01_summary_of_weather.csv
│   ├── 02_weather_station_locations.csv
│   ├── 03_weather_ww2_merged.csv # Output of notebook 01
│   └── 04_weather_ww2_ml_ready.csv # Output of notebook 03
├── 01_load_and_merge.ipynb
├── 02_exploratory_data_analysis.ipynb
├── 03_cleaning_and_feature_engineering.ipynb
└── 04_linear_regression_model.ipynb
```

## Tools and libraries

The project is implemented in Python and uses, at minimum:

- `pandas` for data loading, cleaning, and manipulation
- `numpy` for numerical operations
- `matplotlib` / `seaborn` for visualization
- `scikit-learn` for preprocessing, baselines, and linear regression

Additional libraries may be added as needed (e.g. for geospatial plots or advanced time‑series analysis).

## Author

- [Tümay YILDIZ](https://github.com/YILDIZ17)
