import pandas as pd
import numpy as np
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import LabelEncoder
from sklearn.linear_model import LinearRegression
from sklearn.tree import DecisionTreeRegressor
from sklearn.metrics import mean_squared_error, r2_score
df = pd.read_csv(r"C:\Users\sarve\Downloads\Dataset .csv")
df.drop([
    'Restaurant ID',
    'Restaurant Name',
    'Address',
    'Locality Verbose',
    'Rating color',
    'Rating text',
    'Currency'
], axis=1, inplace=True)
df.fillna(df.mean(numeric_only=True), inplace=True)
df.fillna(df.mode().iloc[0], inplace=True)
label_encoders = {}
categorical_cols = df.select_dtypes(include=['object']).columns

for col in categorical_cols:
    le = LabelEncoder()
    df[col] = le.fit_transform(df[col])
    label_encoders[col] = le
X = df.drop("Aggregate rating", axis=1)
y = df["Aggregate rating"]
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)
lr = LinearRegression()
lr.fit(X_train, y_train)
lr_pred = lr.predict(X_test)
dt = DecisionTreeRegressor(random_state=42)
dt.fit(X_train, y_train)
dt_pred = dt.predict(X_test)
print("Linear Regression Performance:")
print("Mean Squared Error:", mean_squared_error(y_test, lr_pred))
print("R-squared Score:", r2_score(y_test, lr_pred))

print("\nDecision Tree Regression Performance:")
print("Mean Squared Error:", mean_squared_error(y_test, dt_pred))
print("R-squared Score:", r2_score(y_test, dt_pred))
feature_importance = pd.Series(
    dt.feature_importances_, index=X.columns
).sort_values(ascending=False)
print("\nMost Influential Features Affecting Restaurant Ratings:")
print(feature_importance.head(10))
