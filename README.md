Air Quality Index (AQI) Prediction

Business Question
Can we accurately predict the Air Quality Index (AQI) based on the concentrations of key pollutants (PM2.5, CO, NO2, Ozone) to enable real-time air quality monitoring and public health advisories?

Dataset
• Source: AQI-and-Lat-Long-of-Countries.csv
• Size: 16695 rows, 7 columns
• Description: This dataset contains hourly measurements of pollutant sub-indices (CO, Ozone, NO2, PM2.5) and the overall calculated AQI value. It represents typical data collected from urban air quality monitoring stations.

Tools Used
• Python (pandas, numpy): For data loading, cleaning, and manipulation.
• Python (matplotlib, seaborn): For exploratory data analysis and visualization.
• scikit-learn: For model training (Random Forest Regressor, Linear Regression) and performance evaluation.
• Jupyter Notebook: For the interactive development environment and to combine code, visualizations, and narrative.

Key Findings
Strong Feature Correlation: The PM2.5 AQI value showed the strongest correlation with the overall AQI, confirming fine particulate matter as a primary contributor to air quality degradation.
Feature Importance: The model identified PM2.5 and CO as the most significant predictors, providing insights for prioritizing pollution control efforts.
High Model Accuracy: The Random Forest Regressor achieved an R² score of 1.0 and a Mean Absolute Error (MAE) of 0.09 on the test set, indicating near-perfect predictive capability on this dataset.

Recommendations

Deploy for Real-Time Monitoring: The trained model can be integrated into a real-time data pipeline to provide continuous AQI predictions from incoming pollutant sensor data.
Focus on PM2.5 Monitoring: Given its high feature importance, ensure monitoring equipment for PM2.5 is well-maintained and strategically placed.
Develop an Alert System: Use the model's predictions to create an automated alert system that notifies the public, especially sensitive groups, when hazardous AQI levels are forecasted.

Files

AQI-and-Lat-Long-of-Countries.csv: CSV file containing the overall AQI value, and the pollutant sub-indices (CO, Ozone, NO2, PM2.5) 
aqi_prediction.ipynb: The main Jupyter notebook containing the full code, from data loading to model evaluation and visualization.
Aqi dashboard: The dashboard showing model KPIs, feature importance bars, category breakdowns and a world scatter plot.

Methodology
This project follows a standard supervised machine learning pipeline. First, the dataset was loaded and inspected for missing values. Column names were standardized for easier handling. Next, exploratory data analysis (EDA) was performed using pair plots and a correlation heatmap to understand relationships between pollutants and the target variable (AQI).

The data was then split into training (80%) and testing (20%) sets. A Random Forest Regressor was chosen as the primary model due to its robustness, ability to handle non-linear relationships, and capability to output feature importance scores. The model was trained on the training set and evaluated on the unseen test set using metrics like Mean Absolute Error (MAE), Mean Squared Error (MSE), and the R² score. The final step involved visualizing the predicted vs. actual AQI values to visually assess model performance. This approach was chosen to mimic a real-world scenario where a model must generalize to new, unseen data.