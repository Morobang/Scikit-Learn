# Day 04 – Understanding Data

## 🎯 Goals for Today

* Understand what **data** really means in machine learning.
* Learn the difference between **features (X)** and **labels (y)**.
* Learn about **train/test split** and **why it matters**.

---

## 1. **What is Data in Machine Learning?**

Data is the **information we give to the model so it can learn**.

It usually looks like a **table**:

| Size (m²) | Bedrooms | Price (\$) |
| --------- | -------- | ---------- |
| 50        | 1        | 70,000     |
| 80        | 2        | 120,000    |
| 120       | 3        | 200,000    |

* The first two columns are **features** (inputs).
* The last column is **label/target** (what we want to predict).

---

## 2. **Features (X)**

* These are **inputs** used to make predictions.
* They describe each example.
* Examples:

  * Height, weight, and age of a person
  * Size and location of a house

We write them as `X` (uppercase).

---

## 3. **Labels (y)**

* This is the **output** we want to predict.
* Examples:

  * Price of a house
  * Whether an email is spam (yes/no)

We write it as `y` (lowercase).

---

## 4. **Why Split Data?**

We split data into two sets:

* **Training data** – Used to teach the model (like class notes).
* **Testing data** – Used to see if the model learned (like an exam).

**Why?**
If the model sees all the answers during training,
it might just **memorize** instead of **learning**.
We need to check it on **new unseen data**.

---

## 5. **Train/Test Split in Code**

```python
from sklearn.model_selection import train_test_split
from sklearn.datasets import load_iris

# 1. Load dataset
iris = load_iris()
X = iris.data      # features
y = iris.target    # labels

# 2. Split into training and testing
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)

print("Training examples:", len(X_train))
print("Testing examples:", len(X_test))
```

---

## 6. **Practice Idea**

Take any small dataset (Iris or Titanic):

1. Write down:

   * Features (columns you use as inputs)
   * Labels (the column you want to predict)
2. Use `train_test_split` and print how many rows are in training vs testing.

---

## 7. **Why This Matters**

If you **don’t prepare your data correctly**,
even the most powerful model will fail.