# Day 06 – First ML Model: Linear Regression

## 🎯 Goals for Today

* Understand what **Linear Regression** is.
* Learn how to **train your first ML model** using scikit-learn.
* Use your model to **make predictions**.

---

## 1. **What is Linear Regression?**

Linear regression is one of the **simplest machine learning models**.

**Idea:**

> Draw a straight line that best fits the data,
> and use that line to predict new values.

Example:

* Input: House size (square meters)
* Output: House price
* Bigger house → higher price.
  We find the straight line that matches this relationship.

---

## 2. **Real-Life Analogy**

Imagine plotting all house prices vs. house sizes on a graph.
Linear regression tries to draw **one straight line** that goes as close as possible to all those points.
Then, for a new house size, we just **read from the line** to guess the price.

---

## 3. **The Math (Simplified)**

$$
y = m \cdot x + b
$$

* $x$ = input (feature)
* $y$ = output (prediction)
* $m$ = slope (how steep the line is)
* $b$ = intercept (where the line starts)

> Don’t worry — scikit-learn does all the math for us!

---

## 4. **Steps to Train a Linear Regression Model**

1. **Load data**
2. **Split into training and testing**
3. **Create the model**
4. **Fit (train) the model**
5. **Predict using the model**
6. **Evaluate the model**

---

## 5. **Example with Code**

Let’s predict house prices using synthetic data:

```python
import numpy as np
from sklearn.linear_model import LinearRegression
from sklearn.model_selection import train_test_split
import matplotlib.pyplot as plt

# 1. Create simple data
X = np.array([[50], [60], [70], [80], [90]])  # house size
y = np.array([150, 180, 200, 220, 250])       # price in $1000

# 2. Split data into train and test
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)

# 3. Create the model
model = LinearRegression()

# 4. Train (fit) the model
model.fit(X_train, y_train)

# 5. Predict
predictions = model.predict(X_test)

print("Predictions:", predictions)
print("Actual:", y_test)

# 6. Visualize
plt.scatter(X, y, color='blue')  # original data
plt.plot(X, model.predict(X), color='red')  # best fit line
plt.xlabel("House size")
plt.ylabel("Price")
plt.title("Linear Regression Example")
plt.show()
```

---

## 6. **Evaluate Performance**

For regression models, common metrics include:

* **Mean Absolute Error (MAE)**
* **Mean Squared Error (MSE)**
* **R² Score**

Example:

```python
from sklearn.metrics import mean_absolute_error, r2_score

print("MAE:", mean_absolute_error(y_test, predictions))
print("R² score:", r2_score(y_test, predictions))
```

---

## 7. **Key Takeaways**

* Linear regression is **simple but powerful** for predicting numbers.
* The model learns a **straight-line relationship** between inputs and outputs.
* This is your **first machine learning model using scikit-learn!**

---

## 8. **Practice Idea**

* Use the **`load_diabetes()` dataset** from sklearn.
* Train a `LinearRegression` model.
* Print the **predicted values vs actual values**.

---

