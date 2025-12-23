**Air Quality in Seoul: EDA, Public Health Correlation, and Forecasting (2017-2019)**

This project analyzes air pollution data in Seoul, South Korea, investigating the relationship between pollutants and public health (specifically lung cancer) and building predictive models for air quality.

**Project overview**

The study explores the trends of 6 major pollutants (SO2, NO2, CO, O3, PM10, PM2.5) across 25 districts in Seoul and evaluates their long-term impact on lung cancer incidence rates.

**Dataset**

The data was sourced from Kaggle, following the URL- https://www.kaggle.com/datasets/bappekim/air-pollution-in-seoul
    - Measurement Info: Detailed hourly measurement data.
    - Station Info: Locations and details of 25 monitoring stations.
    - Item Info: Thresholds and standards for each pollutant.
    - Lung Cancer Cases: District-wise statistics (2017-2020) used for correlation analysis.

**Tech stack and workflow**
- Language: Python
- Libraries: Pandas, Numpy, Matplotlib, Seaborn, Scikit-learn, Statsmodels
- Workflow:
    1. Data Cleaning: Datetime conversion, handling missing values (nulls), and removing duplicates
    2. Standardization: Harmonizing district names and coordinates; reshaping data from wide to long format.
    3. Integration: Merging measurement data with station metadata and health records into a consolidated `final_table`

**Key insights (EDA)**
- *Pollutant correlation*: A strong correlation (0.83) exists between PM10 and PM2.5, as they often originate from the same sources.
- *Temporal trends*:
    - Particulate matter (PM10, PM2.5) peaks during Spring and Winter.
    - Ozone (O3) levels rise in Summer due to increased solar radiation.
    - CO and NO2 levels are higher on weekdays (peaking Tuesdays) compared to weekends, reflecting traffic and industrial patterns.

**Health impact analysis**
- Correlation: PM10 shows a significant positive correlation (r = 0.53) with lung cancer cases.
- Statistical modelling: Using OLS, Ridge, and Lasso Regression, the study identifies PM10 as the most dominant environmental factor affecting lung health in the long term.
- Clustering: Districts with high pollution levels (e.g., Songpa, Gangnam, Gangseo) consistently fall into clusters with higher lung cancer rates.

**Forecasting models**

Evaluated multiple models to predict pollution levels: 
    - *Linear regression*: Performed best in this scenario, explaining roughly 80% of the variance with an average error of only 6 units.
    - *RandomForest*: Proved robust against outliers in noisy environmental data.
    - *LSTM*: Captured temporal sensitivities but required more intensive preprocessing (e.g., log transformation).

**Conclusion**

The analysis confirms that PM10 is a critical environmental risk factor for public health in Seoul. The predictive models developed can serve as a foundation for early warning systems and urban policy planning.

