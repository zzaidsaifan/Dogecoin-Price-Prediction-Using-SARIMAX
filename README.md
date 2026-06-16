# 🚀 Dogecoin Price Prediction Using SARIMAX Time Series Forecasting

## 📌 Project Overview

Cryptocurrency markets are highly volatile, making accurate price prediction a challenging task. This project focuses on forecasting **Dogecoin (DOGE)** prices using historical market data and a **SARIMAX (Seasonal AutoRegressive Integrated Moving Average with eXogenous Variables)** model.

The project demonstrates a complete Data Science workflow, including:

* Data Collection
* Data Preprocessing
* Exploratory Data Analysis (EDA)
* Feature Engineering
* Correlation Analysis
* Time Series Forecasting
* Model Evaluation through Visualization

The primary goal is to analyze historical Dogecoin price movements and predict future trends using statistical forecasting techniques.

---

## 🎯 Objectives

* Analyze historical Dogecoin market data.
* Understand relationships between market variables.
* Perform exploratory data analysis (EDA).
* Create meaningful engineered features.
* Build a SARIMAX forecasting model.
* Generate future price predictions.
* Visualize actual vs predicted values.

---

## 📊 Dataset Description

The dataset contains historical Dogecoin trading information obtained from Yahoo Finance.

### Features

| Feature   | Description              |
| --------- | ------------------------ |
| Date      | Trading Date             |
| Open      | Opening Price            |
| High      | Highest Price of the Day |
| Low       | Lowest Price of the Day  |
| Close     | Closing Price            |
| Adj Close | Adjusted Closing Price   |
| Volume    | Trading Volume           |

---

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Statsmodels
* Scikit-Learn
* Jupyter Notebook

---

## 🔄 Methodology

### 1. Data Preprocessing

The dataset was cleaned and prepared by:

* Converting Date into datetime format.
* Setting Date as the index.
* Removing missing values.
* Verifying data consistency.

### 2. Exploratory Data Analysis (EDA)

EDA was performed to:

* Understand data distribution.
* Identify trends and patterns.
* Analyze relationships between variables.
* Visualize historical price movements.

### 3. Correlation Analysis

A correlation matrix and heatmap were generated to identify relationships among variables.

**Key Findings:**

* High Price and Close Price are strongly correlated.
* Low Price and Close Price show strong positive correlation.
* Volume contributes additional predictive information.

### 4. Feature Engineering

New features were created to enhance model performance:

#### Gap Feature

```python
gap = (High - Low) * Volume
```

Measures daily volatility weighted by trading activity.

#### Price Ratio Feature

```python
a = High / Low
```

Represents the daily price spread.

#### Volume Adjusted Feature

```python
b = (High / Low) * Volume
```

Combines price movement with trading volume.

### 5. Feature Selection

Selected features used for forecasting:

```python
['Close', 'Volume', 'gap', 'a', 'b']
```

---

## 🤖 Model Development

### SARIMAX Model

The forecasting model used is:

```python
from statsmodels.tsa.statespace.sarimax import SARIMAX

model = SARIMAX(
    endog=train["Volume"],
    exog=train.drop("Volume", axis=1),
    order=(2,1,1)
)
```

### Model Parameters

| Parameter | Value |
| --------- | ----- |
| p         | 2     |
| d         | 1     |
| q         | 1     |

Where:

* **p** = Autoregressive order
* **d** = Differencing order
* **q** = Moving Average order

---

## 📈 Results

The SARIMAX model was trained on historical observations and used to generate forecasts.

Example Prediction:

```text
2022-08-16    0.097293
2022-08-17    0.083717
2022-08-18    0.075957
```

The model successfully captured short-term trends in Dogecoin price movements.

---

## 📉 Visualizations

The project includes:

* Historical Closing Price Trend
* High vs Low vs Close Price Analysis
* Correlation Heatmap
* Actual vs Predicted Price Comparison

These visualizations help understand market behavior and evaluate forecasting performance.

---

## 📂 Project Structure

```bash
Dogecoin-Price-Prediction/
│
├── DOGE-USD.csv
├── Dogecoin_price_prediction.ipynb
├── README.md
└── requirements.txt
```

---

## 🚀 Installation

Clone the repository:

```bash
git clone https://github.com/your-username/Dogecoin-Price-Prediction.git
```

Navigate to the project folder:

```bash
cd Dogecoin-Price-Prediction
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Launch Jupyter Notebook:

```bash
jupyter notebook
```

---

## 📦 Requirements

```text
pandas
numpy
matplotlib
seaborn
scikit-learn
statsmodels
jupyter
```

---

## 📌 Key Insights

* Dogecoin prices exhibit strong relationships between Open, High, Low, and Close values.
* Feature engineering improves forecasting capability.
* SARIMAX effectively models time-dependent financial data.
* Trading volume provides additional predictive information.
* Statistical forecasting techniques can be successfully applied to cryptocurrency markets.

---

## ⚠️ Limitations

* Small training dataset used in forecasting.
* Limited model evaluation metrics.
* No hyperparameter tuning performed.
* No comparison with advanced machine learning models.

---

## 🔮 Future Enhancements

* Implement ARIMA and Prophet models.
* Compare performance with LSTM networks.
* Add MAE, RMSE, and MAPE evaluation metrics.
* Perform hyperparameter optimization.
* Build an interactive dashboard for visualization.

---

## 🎓 Learning Outcomes

This project demonstrates practical knowledge in:

* Data Cleaning
* Exploratory Data Analysis
* Feature Engineering
* Time Series Forecasting
* Financial Data Analytics
* Statistical Modeling
* Python Programming

---

## 👩‍💻 Author

**Zaid Arif Saifan**
*Financial Enginneer*
HEC Montreal, Canada

---

⭐ If you found this project useful, consider giving it a star on GitHub.
