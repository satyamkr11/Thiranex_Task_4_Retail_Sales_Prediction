# Thiranex Internship — Task 4
## Retail Sales Prediction & Business Analytics

[![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python&logoColor=white)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-Machine%20Learning-F7931E?logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![Google Colab](https://img.shields.io/badge/Run%20in-Google%20Colab-F9AB00?logo=googlecolab&logoColor=white)](https://colab.research.google.com/github/satyamkr11/Thiranex_Task_4_Retail_Sales_Prediction/blob/main/Thiranex_Task_4_Retail_Sales_Prediction.ipynb)

An end-to-end retail analytics and machine-learning project completed as part of the **Thiranex Internship — Task 4**.

The project analyses real-world retail transaction data, extracts business insights, engineers time-based and historical sales features, and trains a **Random Forest Regression** model to predict daily revenue.

---

## Project Overview

**Domain:** Retail Analytics & Machine Learning

**Objective:**  
Perform an end-to-end analysis of retail transactions and build a machine-learning model for daily revenue prediction.

### Workflow

1. Load the retail transaction dataset
2. Clean and validate transaction records
3. Calculate transaction-level revenue
4. Perform exploratory data analysis
5. Generate business metrics
6. Aggregate transactions into a daily sales dataset
7. Engineer calendar, lag, and rolling features
8. Split data chronologically into training and testing sets
9. Train a Random Forest regression model
10. Evaluate predictions using MAE, RMSE, and R²
11. Analyse actual vs. predicted revenue
12. Interpret model feature importance

---

## Dataset

This project uses the **Online Retail** dataset from the UCI Machine Learning Repository.

The dataset contains real-world retail transactions with fields including:

- Invoice number
- Product/stock code
- Product description
- Quantity
- Invoice date
- Unit price
- Customer ID
- Country

**Source:**  
https://archive.ics.uci.edu/dataset/352/online+retail

The dataset is **not included in this repository**. The notebook provides a Google Colab upload step so the dataset can be supplied at runtime.

---

## Data Cleaning

The notebook applies the following cleaning rules:

- Converts InvoiceDate to datetime
- Removes duplicate rows
- Removes records missing required transaction fields
- Keeps only positive quantities
- Keeps only positive unit prices
- Calculates Revenue = Quantity × UnitPrice

---

## Exploratory Data Analysis

The project explores retail performance through:

- Monthly revenue trends
- Top products by revenue
- Top countries by revenue
- Total revenue
- Total units sold
- Unique invoices
- Unique products
- Number of countries

The notebook also generates visualisations for the major business patterns.

---

## Feature Engineering

The project creates calendar and historical sales features.

### Calendar Features

- Day
- Month
- Year
- Day of week
- Weekend indicator

### Historical Features

- Lag_1 — previous day's revenue
- Lag_7 — revenue from seven days earlier
- Rolling_7 — previous 7-day average revenue

Additional daily business features include:

- Units
- Transactions
- Products
- Customers

---

## Machine Learning Model

### Random Forest Regression

The prediction model is RandomForestRegressor.

Configuration:

- n_estimators = 250
- max_depth = 12
- min_samples_leaf = 2
- random_state = 42
- n_jobs = -1

A **chronological 80/20 train-test split** is used so that earlier observations are used for training and later observations are reserved for evaluation.

This avoids randomly mixing future observations into the training data.

---

## Model Evaluation

The model is evaluated using:

| Metric | Purpose |
|---|---|
| **MAE** | Average absolute prediction error |
| **RMSE** | Penalises larger prediction errors more strongly |
| **R²** | Measures how much variance is explained by the model |

The notebook also produces:

- Actual vs. predicted daily revenue plot
- Random Forest feature-importance analysis

Run the notebook to generate the numerical evaluation results.

---

## Key Findings

The project demonstrates a complete retail prediction workflow combining:

- Data cleaning
- Exploratory data analysis
- Business metrics
- Time-based feature engineering
- Historical sales features
- Chronological model validation
- Regression modelling
- Model interpretation

The notebook's final sections document the generated analysis and model outputs.

---

## Project Structure

    Thiranex_Task_4_Retail_Sales_Prediction/
    │
    ├── Thiranex_Task_4_Retail_Sales_Prediction.ipynb
    ├── README.md
    ├── requirements.txt
    ├── .gitignore
    └── LICENSE

---

## How to Run

### Option 1 — Google Colab

Open the notebook directly in Google Colab:

**Open in Google Colab:**  
https://colab.research.google.com/github/satyamkr11/Thiranex_Task_4_Retail_Sales_Prediction/blob/main/Thiranex_Task_4_Retail_Sales_Prediction.ipynb

Then:

1. Run the first cell.
2. Upload the Online Retail Excel dataset.
3. Run the remaining cells from top to bottom.
4. Review the generated visualisations, business metrics, and model evaluation.

### Option 2 — Local Environment

Clone the repository:

    git clone https://github.com/satyamkr11/Thiranex_Task_4_Retail_Sales_Prediction.git
    cd Thiranex_Task_4_Retail_Sales_Prediction

Install dependencies:

    pip install -r requirements.txt

Launch Jupyter:

    jupyter notebook

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Jupyter Notebook
- Google Colab

---

## Future Improvements

Potential extensions include:

- Hyperparameter tuning
- Advanced time-series forecasting
- Product-level demand forecasting
- Customer segmentation
- Interactive dashboards
- Model comparison with Gradient Boosting/XGBoost
- Automated model deployment

---

## Internship

**Program:** Thiranex Internship  
**Task:** Task 4 — Retail Sales Prediction & Business Analytics

---

## License

This project is available under the **MIT License**.
