# Day 02 – ML Basics and Terminology

## 🎯 Goals for Today

* Understand what **Machine Learning (ML)** is.
* Learn the **types of ML**.
* Get familiar with **common ML terms**.

---

## 1. **What is Machine Learning?**

**Simple explanation:**
Machine Learning is teaching computers to **learn from data** instead of explicitly programming them.

Instead of telling a computer step-by-step rules,
we give it **examples (data)** and it figures out the rules by itself.

### Real-world examples:

* Netflix recommends movies (learns from your watch history).
* Email spam filters (learn from past spam emails).
* Self-driving cars (learn from millions of driving scenarios).

---

## 2. **How Does It Work?**

Think of ML like this:

1. **Data (Input):** Past examples (e.g., house size, price)
2. **Model:** The learning brain
3. **Training:** Feed the model data so it can find patterns
4. **Prediction:** Use the trained model to make guesses on new data

---

## 3. **Types of Machine Learning**

There are three main types:

### **1. Supervised Learning**

* **We have inputs and known answers (labels).**
* The model learns from these examples.
* Example: Predicting house prices (input = size; output = price).

> Like a teacher giving correct answers so the student can learn.

**Tasks:**

* Regression (predict a number)
* Classification (predict a category)

---

### **2. Unsupervised Learning**

* **We only have inputs (no answers).**
* The model tries to find hidden patterns or groupings.
* Example: Grouping customers by buying behavior.

> Like students figuring things out with no teacher.

**Tasks:**

* Clustering (grouping similar things)
* Dimensionality reduction (compressing data)

---

### **3. Reinforcement Learning**

* **The model learns by trial and error.**
* It gets rewards for good actions, penalties for bad ones.
* Example: Training a robot to walk or an AI to play chess.

> Like teaching a dog tricks with rewards.

---

## 4. **Key ML Terminology**

Here are the essential terms:

### **Dataset**

Collection of data. Example: table with columns and rows.

### **Features (X)**

Input variables. Example: "size", "number of rooms".

### **Labels/Target (y)**

Output variable we want to predict. Example: "price".

### **Training Data**

Data we use to teach the model.

### **Testing Data**

New data used to check if the model learned well.

### **Model**

The algorithm that learns from data and makes predictions.

### **Prediction**

What the model guesses based on new data.

---

## 5. **Why Split Data?**

If we train and test on the same data,
the model just memorizes instead of learning.
Testing on **new unseen data** checks if it really learned patterns.

---

## 6. **Visual Example**

Imagine you are learning to recognize fruits:

* You study many images of apples and bananas (**training**).
* Later, I show you a new fruit photo.
  If you say “apple” or “banana” correctly (**prediction**),
  that means you **learned patterns** like color and shape.

---

## 7. **Today’s Deliverable**

* Be able to explain:

  * Difference between **supervised, unsupervised, and reinforcement learning**
  * Terms: features, labels, training data, testing data
* Draw a simple diagram like this in your notebook:

```
Data -> Train Model -> Model -> Predictions
```
