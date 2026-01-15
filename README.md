# Restaurant Rating Prediction

Predict restaurant ratings using machine learning models based on restaurant features.

## Overview
This project predicts the **aggregate rating** of restaurants using various features such as location, cuisine, cost, and votes. It demonstrates **data preprocessing, encoding categorical variables, training regression models**, and identifying the most influential features.

## Dataset
The dataset contains restaurant information including:
- Location and locality
- Cuisine type
- Cost for two people
- Votes
- Aggregate ratings

Unnecessary columns such as `Restaurant ID`, `Restaurant Name`, `Address`, and currency details are removed during preprocessing.

## Steps

### 1. Data Preprocessing
- Remove irrelevant columns.
- Handle missing values:
  - Numeric → replaced with mean
  - Categorical → replaced with mode
- Encode categorical columns using `LabelEncoder`.

### 2. Model Training
- Split data into training (80%) and test (20%) sets.
- Train two regression models:
  - **Linear Regression**
  - **Decision Tree Regression**

### 3. Evaluation
- Evaluate models using:
  - Mean Squared Error (MSE)
  - R² Score
- Compare model performance to determine the best approach.

### 4. Feature Importance
- Use Decision Tree Regression to identify the top features influencing restaurant ratings.

## How to Run
1. Clone this repository.
2. Ensure the dataset CSV file is available and update the path in the script.
3. Install required libraries:
bash
pip install pandas numpy scikit-learn
Run the Python script:

bash
Copy code
python restaurant_rating_prediction.py
Insights
Machine learning models can predict restaurant ratings effectively.

Decision Tree Regression helps understand which factors (votes, cost, cuisine, etc.) have the most impact on ratings.
