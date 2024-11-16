# Car Price Prediction Project

This repository contains a project focused on predicting car prices using machine learning techniques. The project follows the **CRISP-DM (Cross Industry Standard Process for Data Mining)** methodology to ensure a systematic and structured approach.

Jupyter Notebook:
Graph:

## Business Understanding
- **Objective**: Provide a predictive model that helps users and dealerships estimate car prices based on specific attributes.
- **Goal**:
  - Identify factors that significantly influence car prices.
  - Use these insights to assist dealerships in optimizing inventory pricing strategies.
  
---

## Data Understanding
- The dataset contains **426,880 rows** and **18 columns**, including:
  - Key Features: `odometer`, `year`, `condition`, `manufacturer`, `fuel`, and more.
  - Target Variable: `price` (log-transformed for better modeling).
- **Initial Analysis**:
  - Missing data in critical columns like `condition` and `VIN`.
  - Outliers in features such as `year` and `odometer`.

---

## Data Preparation
- Steps taken:
  - Dropped or imputed missing values for critical features.
  - One-hot encoded categorical variables (`manufacturer`, `transmission`, etc.).
  - Removed or capped outliers in numerical features like `price` and `odometer`.
  - Log-transformed the `price` variable for normalization.

---

## Modeling
- Algorithms applied:
  1. **Linear Regression**:
     - Baseline model for comparison.
     - \( R^2 \): ~5.9%, indicating weak linear relationships.
  2. **Ridge Regression**:
     - Regularization improved stability.
     - \( R^2 \): ~5.9%, with slightly better generalization.
  3. **Lasso Regression**:
     - Feature selection identified key predictors.
     - \( R^2 \): ~5.0%.
- **Top Features Identified**:
  - `year`, `condition`, `manufacturer_ferrari`, `manufacturer_tesla`, `transmission_manual`.

---

## Evaluation
- **Metrics Used**:
  - Mean Squared Error (MSE): Average squared prediction error.
  - \( R^2 \): Proportion of variance explained by the model.
  - 
- **Insights**:
  - Current models explain limited variance, suggesting:
    - Need for additional features.
    - Exploration of non-linear models like Random Forest or Gradient Boosting.
    - Newer cars and cars with low mileage are more expensive.
    - For coeficients large positive coefficients are associated with higher car prices. large negative coefficients are associated with lower car prices.
      - Positivie: a car with a newer manufacturing year may have a positive coefficient, indicating that newer cars are more expensive.
      - Negative: a higher odometer reading may have a negative coefficient, suggesting that cars with more mileage are less expensive.
    - Positive Impact feautures influecing Price:
        Transmission Types: transmission_other, transmission_manual, and transmission_automatic have high positive coefficients, indicating that these options significantly affect the price.
        High-End Manufacturers: Brands like Ferrari, Aston-Martin, and Porsche contribute positively to price, which aligns with expectations.
        Condition: Cars in "like new" or "excellent" condition are valued higher than those in poorer condition.
    - Negative Impact Feautures influencing price:
        Manufacturer Land Rover: A significantly negative coefficient suggests that this brand is undervalued compared to others in the dataset.
        Year: The small positive coefficient (3.594571e-03) shows that newer cars are slightly more expensive, but this feature may be dwarfed by others
    - Luxury manufacturers and better car conditions significantly increase prices.
    - Transmission types also play a significant role, with less common types being more expensive.
    - Outliers in features like year (e.g., very old cars) and price (e.g., cars with 0 price) may distort model performance.
    - Missing data in critical features (condition, drive, fuel, etc.) reduces the reliability of the analysis.




---

## Deployment and Reccomendations
- Next Steps:
  - Enhance model performance with advanced algorithms.
  - Handle Missing Data:Impute missing values or drop rows where critical features like condition are missing.
  - Outlier Treatment:Remove or cap outliers in price, year, and odometer.
  - Non-Linear Models:Try tree-based models like Random Forest or Gradient Boosting to capture complex relationships.
  - Expand Features: Include features like drive, size, and type to improve model explanatory power.

---

## Technologies Used
- **Programming Languages**: Python
- **Libraries**:
  - Data Processing: `pandas`, `numpy`
  - Visualization: `matplotlib`, `seaborn`
  - Machine Learning: `scikit-learn`
- **Version Control**: Git, GitHub

---
