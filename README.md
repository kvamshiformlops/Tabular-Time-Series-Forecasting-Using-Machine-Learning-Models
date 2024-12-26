# Video Game Sales Analysis and Forecasting

This project involves analyzing a video game sales dataset, cleaning and preprocessing the data, and building machine learning models to forecast future sales. The project includes comprehensive exploratory data analysis (EDA), data preprocessing, and implementation of multiple machine learning models for forecasting.

---

## Table of Contents

1. [Dataset Overview](#dataset-overview)
2. [Data Preprocessing](#data-preprocessing)
3. [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
4. [Machine Learning Models](#machine-learning-models)
   - Random Forest Regressor
   - XGBoost Regressor
   - LightGBM Regressor
   - Support Vector Regressor (SVR)
   - ARIMA
   - SARIMAX
5. [Evaluation Metrics](#evaluation-metrics)
6. [Results and Insights](#results-and-insights)
7. [License](#license)

---

## Dataset Overview

The dataset used for this project is sourced from VGChartz and contains information about video game sales, including:

- Title, Console, Genre, Publisher, Developer
- Sales in different regions: NA, JP, PAL, Other
- Critic Score and Total Sales
- Release Date and Last Update

---

## Data Preprocessing

1. **Handling Missing Values:**

   - Text columns (e.g., title, genre) were filled with 'Unknown'.
   - Sales columns were converted to numeric types, and missing values were imputed using the median.
   - Critic scores were clipped between 0 and 100.

2. **Feature Engineering:**

   - Dropped unnecessary columns: `img`, `release_date`, `last_update`.
   - Encoded categorical columns using `LabelEncoder`.

3. **Outlier Removal:**

   - Used Z-Score normalization to detect and remove outliers.

4. **Sequential Data Preparation:**

   - Created supervised learning data for time series forecasting with a window size of 60 time steps.

---

## Exploratory Data Analysis (EDA)

1. Displayed the first and last few rows of the dataset.
2. Generated summary statistics for numerical columns.
3. Examined dataset shape, column names, and information.
4. Calculated skewness and kurtosis for numerical columns.

---

## Machine Learning Models

### Random Forest Regressor

- A robust ensemble model was used to predict sales.
- Features: `genre`, `critic_score`, `na_sales`, `jp_sales`, `pal_sales`, `other_sales`.

### XGBoost Regressor

- A gradient-boosting algorithm known for its performance and speed.
- Tuned with parameters: `n_estimators=100`, `learning_rate=0.1`, `max_depth=6`.

### LightGBM Regressor

- A lightweight gradient-boosting model optimized for speed and efficiency.
- Tuned similarly to XGBoost.

### Support Vector Regressor (SVR)

- SVR is a powerful regression algorithm that fits a hyperplane in a higher-dimensional space to predict values.
- Implemented with a **radial basis function (RBF) kernel** and tuned using hyperparameters such as `C`, `epsilon`, and `kernel`.
- Features: `genre`, `critic_score`, `na_sales`, `jp_sales`, `pal_sales`, `other_sales`.

### ARIMA

- Traditional statistical model used for univariate time series forecasting.
- Configured with order `(3, 0, 2)`.

### SARIMAX

- Extended ARIMA model to capture seasonal patterns.
- Configured with order `(3, 0, 2)` and seasonal order `(3, 0, 2, 12)`.

---

## Evaluation Metrics

The models were evaluated using the following metrics:

- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)
- R-Squared (R²) Score
- Explained Variance Score (EVS)

---

## Results and Insights

- **Random Forest Regressor:** Performed well with minimal overfitting.
- **XGBoost and LightGBM:** Achieved high accuracy and efficiency.
- **Support Vector Regressor (SVR):** Demonstrated competitive performance, especially for medium-sized datasets.
- **ARIMA and SARIMAX:** Suitable for capturing temporal dependencies but less competitive with ensemble models for this dataset.

---

## License

This project is licensed under the MIT License.

