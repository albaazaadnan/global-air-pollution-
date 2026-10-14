# Global Air Pollution

An exploratory analysis of air quality observations across countries and cities. The project is presented as a Jupyter notebook for a data visualization course.

## Goal

Explore how air quality varies across locations and pollutant indicators. The analysis focuses on AQI (Air Quality Index) patterns, comparisons between AQI and pollutant-specific indicators, and geographic differences.

## Data

The notebook expects a file named `global_air_pollution.csv` in the project directory. It contains 23,463 rows and 12 columns in the saved notebook output, with country and city names, overall AQI value and category, and AQI values and categories for CO, ozone, NO2, and PM2.5.

The notebook reports 427 missing country values and one missing city value. It drops rows missing either location field, leaving 23,035 observations for the analysis. The CSV is not currently included in this project folder, so add the dataset before running the notebook. The notebook does not identify the dataset's original publisher or collection period.

## Method

The analysis is in [`Visualisation_donnees.ipynb`](Visualisation_donnees.ipynb). It uses:

- **Pandas and NumPy** to load, clean, summarize, and group the data.
- **Matplotlib and Seaborn** for univariate distributions and bivariate comparisons.
- **Plotly** for interactive charts and country-level choropleth maps.
- **Scikit-learn PCA** to scale pollutant indicators and explore their principal components.
- **GeoPandas, GeoDatasets, GeoPy, and Shapely** for geographic views, including geocoding selected cities.

To run it, place `global_air_pollution.csv` beside the notebook, install the libraries imported in the notebook, and open the notebook in Jupyter. The geocoding cells use the Nominatim service and need network access.

## Results

The notebook's saved analysis reports these main findings:

- PM2.5 AQI and overall AQI have a Pearson correlation of **0.985**; ozone AQI and overall AQI have a correlation of **0.405**. In this dataset, PM2.5 tracks overall AQI especially closely. This is an association, not evidence that PM2.5 alone causes the overall AQI; the indicators may also be related by how AQI is defined.
- Good and Moderate are the most common AQI categories, reported as approximately **42%** and **39%** of observations.
- The first two principal components explain about **79.7%** of the variance; the first three explain about **93.1%**.
- Country averages and city comparisons show substantial geographic variation. The notebook highlights high average AQI in the Republic of Korea and high counts of unhealthy observations in India. These are descriptive results from the dataset and depend on its coverage and observation counts.

These results are transcribed from the notebook's saved outputs and interpretation. Re-run the notebook with the source CSV to reproduce the charts and confirm the figures.
