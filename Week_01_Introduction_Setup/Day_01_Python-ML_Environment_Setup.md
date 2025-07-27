# Day 01 – Python-ML Environment Setup

## 🎯 **Goals for Today**

* Set up your Python environment for machine learning.
* Install essential packages (scikit-learn, pandas, numpy, matplotlib, seaborn, jupyter).
* Verify that everything works.

---

## 1. **Install Python**

* Download Python 3.10+ from [https://www.python.org/downloads/](https://www.python.org/downloads/)
* During installation:

  * Check **"Add Python to PATH"**.
  * Verify installation:

    ```bash
    python --version
    ```

---

## 2. **Set up a Virtual Environment**

A virtual environment isolates your projects and dependencies.

```bash
# Create a folder for your ML projects
mkdir ml_projects
cd ml_projects

# Create virtual environment
python -m venv venv

# Activate:
# Windows
venv\Scripts\activate
# Mac/Linux
source venv/bin/activate
```

To deactivate later:

```bash
deactivate
```

---

## 3. **Install Jupyter Notebook**

```bash
pip install notebook
```

Launch Jupyter:

```bash
jupyter notebook
```

---

## 4. **Install Core Libraries**

```bash
pip install numpy pandas matplotlib seaborn scikit-learn
```

Optional (if using visual studio code):

```bash
pip install ipykernel
```

---

## 5. **Verify Installation**

Create a notebook and run:

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
import sklearn

print("NumPy:", np.__version__)
print("Pandas:", pd.__version__)
print("Scikit-learn:", sklearn.__version__)
```

If all versions print correctly—you're good to go!

---

## 6. **Folder Structure for This Course**

```
90_Days_ScikitLearn/
  Week_01_Introduction_Setup/
    Day_01_Python-ML_Environment_Setup.md
    Day_02_ML_Basics_and_Terminology.md
    ...
```

---

## **Today’s Deliverable**

* Screenshot of:

  * Jupyter Notebook running `print("Hello ML")`
  * Output of version check for all libraries.

---

