
# Car Selling Price Prediction

This project aims to predict the selling price of cars using car_details.csv containing various features such as car name, year, driven distance, fuel type, seller type, transmission, owner type, mileage, engine size, max power, and number of seats.

## Project Steps

1.  **Data Loading**: Loaded the car details dataset into a pandas DataFrame.
2.  **Exploratory Data Analysis (EDA)**:
    *   Displayed the first few rows and basic statistics.
    *   Checked for null values and dropped rows with missing data.
    *   Detected and visualized outliers in numerical columns using box plots and the IQR method.
    *   Removed outliers from numerical columns.
    *   Identified categorical columns.
3.  **Data Preprocessing**:
    *   Performed one-hot encoding on 'fuel', 'seller_type', 'transmission', and 'owner' columns.
    *   Dropped the 'name' and 'max_power' columns for modeling in this iteration.
4.  **Model Training**:
    *   Split the data into training and testing sets (80/20 split).
    *   Trained a **Random Forest Regressor** model.
    *   Trained an **XGBoost Regressor** model.
5.  **Model Evaluation**:
    *   Evaluated both models using R² Score, Root Mean Squared Error (RMSE), and Mean Absolute Error (MAE).
    *   Visualized the performance comparison using a bar plot.
    *   Visualized the actual vs. predicted selling prices for the XGBoost model using a scatter plot.
6.  **Feature Importance**:
    *   Analyzed feature importance from the XGBoost model to understand the influence of different features on selling price.

## Model Performance

The performance of the trained models is as follows:

*   **Random Forest Regressor**:
    *   R² Score: {{r2_rf:.2f}}
    *   RMSE: {{rmse_rf:.2f}}
    *   MAE: {{mae_rf:.2f}}

*   **XGBoost Regressor**:
    *   R² Score: {{r2_xgb:.2f}}
    *   RMSE: {{rmse_xgb:.2f}}
    *   MAE: {{mae_xgb:.2f}}

Based on the R² and RMSE values, the XGBoost Regressor performed slightly better on this dataset.

## Key Feature Insights

The feature importance analysis using the XGBoost model revealed that:

*   **Year** is the most significant factor influencing car selling prices.
*   **Engine size** and **Seller Type (Trustmark Dealer)** are the next most important features.
*   Other features like mileage, transmission, and fuel type also contribute to the prediction.
*   The number of seats did not appear to be a significant predictor after outlier removal.

## Future Work

*   Further explore and potentially engineer features from the 'name' and 'max_power' columns.
*   Perform hyperparameter tuning for the XGBoost model to potentially improve performance.
*   Investigate other regression models.
*   Implement cross-validation for more robust model evaluation.
