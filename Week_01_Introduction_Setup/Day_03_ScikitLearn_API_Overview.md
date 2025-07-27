# Day 03 – Scikit-Learn API Overview

## 🎯 Goals for Today

* Understand what **Scikit-Learn** is and why we use it.
* Learn about the **main workflow**:
  `load data → create model → fit → predict → evaluate`.
* Get comfortable with the **fit/predict/transform** pattern.

---

## 1. **What is Scikit-Learn?**

Scikit-Learn (sklearn) is a **Python library** that makes machine learning simple.

Think of it like a **toolbox full of ready-made algorithms**:

* Regression
* Classification
* Clustering
* Preprocessing tools (scaling, splitting, etc.)

Instead of coding ML algorithms from scratch,
we just **import the right tool and use it**.

---

## 2. **The Core Idea**

Almost every ML task in Scikit-Learn follows the same **4 steps**:

```
1. Load and prepare data
2. Choose a model (algorithm)
3. Fit (train) the model on the data
4. Use the model to predict new results
```

This pattern is very consistent, which makes sklearn easy to learn.

---

## 3. **The Estimator API**

In sklearn, **models and preprocessors are called Estimators**.

An **Estimator** is any object with:

* `.fit()` method: learns from data
* `.predict()` method: makes predictions (if it’s a model)
* `.transform()` method: transforms data (if it’s a preprocessor)

**Key rule:**

> If it can learn, it has a `.fit()` method.

---

## 4. **Basic Workflow (Step by Step)**

### **1. Load Data**

Sklearn has built-in datasets for practice:

```python
from sklearn import datasets

data = datasets.load_iris()
X = data.data     # features
y = data.target   # labels
```

You can also use pandas to load CSV files.

---

### **2. Split Data into Train and Test**

```python
from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42)
```

We use 80% of data for training and 20% for testing.

---

### **3. Choose a Model**

Example: A simple Decision Tree.

```python
from sklearn.tree import DecisionTreeClassifier

model = DecisionTreeClassifier()
```

This `model` is an estimator.

---

### **4. Fit (Train) the Model**

```python
model.fit(X_train, y_train)
```

The model **learns patterns** from the training data.

---

### **5. Predict**

```python
predictions = model.predict(X_test)
```

The model guesses labels for new unseen data.

---

### **6. Evaluate**

```python
from sklearn.metrics import accuracy_score
print("Accuracy:", accuracy_score(y_test, predictions))
```

This tells us how good the model is.

---

## 5. **Important Scikit-Learn Functions**

* **`fit()`** – Learn from data
* **`predict()`** – Predict new values (models only)
* **`transform()`** – Modify data (preprocessors only)
* **`fit_transform()`** – Do both at once (common for scaling)

---

## 6. **Key Idea to Remember**

> **fit → predict/transform**
> This is the heart of Scikit-Learn.

Whenever you see a new sklearn function,
ask: **Does it learn (fit)? Does it predict or transform?**

---

## 7. **Your Practice for Today**

* Write a notebook that:

  1. Loads the `iris` dataset
  2. Splits it into train/test
  3. Trains a `DecisionTreeClassifier`
  4. Prints accuracy

---
