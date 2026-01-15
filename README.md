# Restaurant Rating Prediction 🍽️

Predicting restaurant ratings using machine learning to understand what influences how people rate restaurants.

---

## 🚀 Project Overview
This project aims to predict the **aggregate rating** of restaurants based on various features like location, cuisine type, cost for two, and votes. It demonstrates **data preprocessing, encoding categorical data, training regression models**, and analyzing feature importance.

---

## 🗂 Dataset
The dataset contains:
- Restaurant location and locality
- Cuisine type
- Cost for two
- Votes
- Aggregate ratings

Unnecessary columns like `Restaurant ID`, `Restaurant Name`, `Address`, `Currency`, and textual ratings are removed during preprocessing.

---

## 🔧 Key Steps

### 1️⃣ Data Preprocessing
- Drop irrelevant columns.
- Handle missing values:
  - Numeric → replaced with mean
  - Categorical → replaced with mode
- Encode categorical features using `LabelEncoder`.

### 2️⃣ Model Training
- Split data: 80% training, 20% testing.
- Train regression models:
  - **Linear Regression**
  - **Decision Tree Regression**

### 3️⃣ Model Evaluation
- Metrics used:
  - Mean Squared Error (MSE)
  - R² Score
- Compare model performance.

### 4️⃣ Feature Analysis
- Use Decision Tree to find **top features** affecting restaurant ratings (e.g., votes, cost, type of cuisine).

---

## ⚡ How to Run
1. Clone this repository.
2. Place your dataset CSV file and update the path in the script.
3. Install dependencies:

bash
pip install pandas numpy scikit-learn
Run the script:

bash
Copy code
python restaurant_rating_prediction.py
📊 Insights
Machine learning can effectively predict restaurant ratings.

Decision Tree Regression helps reveal the most influential features, giving insights for restaurant owners and analysts.

💡 Future Improvements
Use advanced models like Random Forest or XGBoost for better accuracy.

Add visualizations for feature importance and predicted vs actual ratings.

Deploy as a web app for real-time rating predictions.
