# **Regression of Used Car Prices**

This project is a regression analysis of used car prices, where the goal is to predict the price of a car based on various features such as brand, model, mileage, fuel type, and more. The project is part of the "Playground Series - Season 4, Episode 9" Kaggle competition.

## **Project Overview**

In this project, we use a dataset of used car listings to train machine learning models to predict car prices. The dataset has been generated using a deep learning model and closely resembles the real-world used car market data. Multiple regression models have been evaluated to predict car prices, with the best model being selected for submission.

### **Dataset Description**

- **train.csv**: The training dataset containing features and the target variable (price).
- **test.csv**: The test dataset with similar features, but without the price column.
- **sample_submission.csv**: A sample submission file in the correct format for the competition.

### **Files in the Repository**
- `train.csv`: Training data with 188,533 rows and 13 columns.
- `test.csv`: Test data with 125,690 rows and 12 columns.
- `sample_submission.csv`: A sample submission file.
- `submission.csv`: Generated file containing the predicted prices for the test data.

## **Setup**

To run the project, you will need the following libraries:
```bash
pandas
numpy
matplotlib
seaborn
scikit-learn
xgboost
lightgbm
catboost
```

## **Exploratory Data Analysis (EDA)**

- **Missing Values**: Missing values were found in columns like `fuel_type`, `accident`, and `clean_title`. These were handled by filling with appropriate values such as 'Electricity' for `fuel_type` and 'No' for `clean_title`.
- **Feature Engineering**: New features such as `car_age`, `horsepower`, `engine_size`, and `cylinder_count` were extracted from the raw `engine` column. Frequency encoding was applied to high-cardinality categorical features like `brand`, `model`, `ext_col`, and `int_col`.

## **Model Training and Evaluation**

### **Models Used:**
1. **Linear Regression**
2. **Random Forest Regressor**
3. **XGBoost Regressor**
4. **LightGBM Regressor**
5. **CatBoost Regressor**

The evaluation metric used was Root Mean Squared Error (RMSE) on the validation set.

### **Model Performance:**
| Model                  | RMSE      |
|------------------------|-----------|
| Linear Regression       | 74,057.20 |
| Random Forest Regressor | 77,652.59 |
| XGBoost Regressor       | 73,066.69 |
| LightGBM Regressor      | 72,181.72 |
| CatBoost Regressor      | **72,098.31** |

**Best Model**: The CatBoost Regressor was selected as the best model based on its performance on the validation set.

## **Feature Engineering and Encoding**

- **Numerical Features**: `horsepower`, `engine_size`, `cylinder_count`, `num_speeds`, etc., were imputed where missing values existed.
- **Categorical Features**: High-cardinality categorical columns (`brand`, `model`, `ext_col`, and `int_col`) were encoded using frequency encoding.
- **Label Encoding**: Applied to `fuel_type` and `transmission_type`.

## **Submission**

The best-performing model (CatBoost) was trained on the full training dataset, and predictions were made on the test dataset. The results were saved in `submission.csv` for submission.

## **Conclusion**

This project demonstrates the use of various machine learning regression models to predict car prices based on a variety of car attributes. After experimenting with several models, CatBoost Regressor proved to be the most effective.

Feel free to explore the code and improve the model further!


 
