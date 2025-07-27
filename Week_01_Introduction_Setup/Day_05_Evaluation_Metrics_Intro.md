# Day 05 – Evaluation Metrics Intro

## 🎯 Goals for Today

* Understand **why accuracy alone is not enough**.
* Learn the most important **evaluation metrics**:

  * Accuracy
  * Precision
  * Recall
  * F1-Score
* Learn how to calculate these metrics in Scikit-Learn.

---

## 1. **Why Do We Need Evaluation Metrics?**

After training a model, we need a way to **measure how good it is**.

**Example:**

* A spam filter marks 95 out of 100 emails correctly.
  Sounds good? Maybe…
* But if it mislabels an important email as spam, that’s a big problem!

This is why we need **metrics that tell the full story**, not just accuracy.

---

## 2. **Key Terms: TP, FP, TN, FN**

Before we learn metrics, we need these terms:

* **True Positive (TP)**: Model predicted "Yes" and it was actually "Yes".
* **True Negative (TN)**: Model predicted "No" and it was actually "No".
* **False Positive (FP)**: Model predicted "Yes" but it was "No". (Type I error)
* **False Negative (FN)**: Model predicted "No" but it was "Yes". (Type II error)

Think of a COVID test:

* **FP** = healthy person marked as positive
* **FN** = sick person marked as negative

---

## 3. **Accuracy**

**What is it?**

> Out of all predictions, how many were correct?

$$
Accuracy = \frac{TP + TN}{TP + TN + FP + FN}
$$

**Good for:**

* When classes are balanced (same amount of Yes and No)

**Problem:**

* If 95% of emails are "not spam", a model that always says "not spam" has 95% accuracy — but it’s useless!

---

## 4. **Precision**

**What is it?**

> Of the items the model said are "Yes", how many were actually "Yes"?

$$
Precision = \frac{TP}{TP + FP}
$$

**Good for:**

* When false alarms are very bad (e.g., flagging innocent people as criminals)

---

## 5. **Recall (Sensitivity)**

**What is it?**

> Of all the actual "Yes" items, how many did the model catch?

$$
Recall = \frac{TP}{TP + FN}
$$

**Good for:**

* When missing a "Yes" is very bad (e.g., detecting cancer)

---

## 6. **F1-Score**

**What is it?**

> Combines Precision and Recall into a single score.

$$
F1 = 2 \cdot \frac{Precision \cdot Recall}{Precision + Recall}
$$

**Why use it?**

* When you want a balance between precision and recall.

---

## 7. **Code Example**

```python
from sklearn.metrics import accuracy_score, precision_score, recall_score, f1_score
from sklearn.datasets import load_iris
from sklearn.model_selection import train_test_split
from sklearn.tree import DecisionTreeClassifier

# Load and split data
iris = load_iris()
X_train, X_test, y_train, y_test = train_test_split(
    iris.data, iris.target, test_size=0.2, random_state=42)

# Train a model
model = DecisionTreeClassifier()
model.fit(X_train, y_train)

# Make predictions
y_pred = model.predict(X_test)

# Evaluate
print("Accuracy:", accuracy_score(y_test, y_pred))
print("Precision:", precision_score(y_test, y_pred, average='macro'))
print("Recall:", recall_score(y_test, y_pred, average='macro'))
print("F1 Score:", f1_score(y_test, y_pred, average='macro'))
```

> **Note:** For multi-class problems, we use `average='macro'`.

---

## 8. **Key Takeaways**

* **Accuracy** is easy but sometimes misleading.
* **Precision** and **Recall** focus on quality of predictions.
* **F1-Score** balances them both.

---