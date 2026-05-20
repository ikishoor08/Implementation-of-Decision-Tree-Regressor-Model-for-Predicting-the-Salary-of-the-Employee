# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.1.Import pandas

2.Import Decision tree classifier

3.Fit the data in the model

4.Find the accuracy score

## Program:
```
/*
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: KISHOOR I
RegisterNumber:  212225040190
*/
import pandas as pd

# Load dataset
data = pd.read_csv("Salary.csv")

# Display dataset
print(data.head())

# Dataset info
print(data.info())

# Check null values
print(data.isnull().sum())

# Label Encoding
from sklearn.preprocessing import LabelEncoder

le = LabelEncoder()

data["Position"] = le.fit_transform(data["Position"])

print(data.head())

# Features and target
x = data[["Position", "Level"]]

print(x.head())

y = data["Salary"]

print(y.head())

# Train-test split
from sklearn.model_selection import train_test_split

x_train, x_test, y_train, y_test = train_test_split(
    x, y, test_size=0.2, random_state=2
)

# Decision Tree Regressor
from sklearn.tree import DecisionTreeRegressor

dt = DecisionTreeRegressor()

# Train model
dt.fit(x_train, y_train)

# Predictions
y_pred = dt.predict(x_test)

print("Predicted values:")
print(y_pred)

# R2 Score
from sklearn.metrics import r2_score

r2 = r2_score(y_test, y_pred)

print("R2 score:", r2)

# Predict new value
prediction = dt.predict([[5, 6]])

print("Prediction for [5,6]:")
print(prediction) 
*/
```

## Output:


<img width="958" height="299" alt="image" src="https://github.com/user-attachments/assets/2af8c1a7-ee3c-438f-9603-8cd2f55d6b67" />
<img width="399" height="195" alt="image" src="https://github.com/user-attachments/assets/f3f8e324-72e6-41cf-b0d1-46c1cc1b6a51" />
<img width="697" height="131" alt="image" src="https://github.com/user-attachments/assets/44099b3e-d3b6-4b7d-ac03-5c838051bbf2" />



## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
