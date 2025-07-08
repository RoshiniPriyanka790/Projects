# **Product Trend Forecasting & Real-Time ML Pipeline (Azure ML, ARIMA, Prophet, LSTM)**

This repository contains a project focused on predicting **volatility patterns** in product trends using **time series forecasting** techniques. We applied multiple forecasting models, including **ARIMA**, **Prophet**, and **LSTM (Long Short-Term Memory)**, to capture high-frequency fluctuations and improve prediction accuracy. The goal of this project is to analyze product trends and forecast potential surges in market activity. By using these models, the project demonstrates how machine learning and traditional time series techniques can be leveraged to predict market or product performance.

The **LSTM model** is deployed as a **real-time REST API** for continuous predictions and alerting, providing instant metric predictions.

---

## **Key Features**
* **Time Series Forecasting Models**: ARIMA, Prophet, and LSTM for predicting product trend volatility.
* **Real-Time API Deployment**: LSTM model deployed using **Azure ML** as a REST API, providing instant predictions and alerts.
* **Model Retraining**: **Azure DevOps CI/CD** pipeline to automate the weekly retraining of the model to maintain production accuracy.
* **Data Visualization**: **Power BI** dashboards used to visualize trend spikes and forecast shifts for actionable insights.

---

## **Installation & Setup**

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/product-trend-forecasting.git
    ```

2. Install necessary Python dependencies:
    ```bash
    pip install -r requirements.txt
    ```

3. Setup Azure ML for LSTM deployment:
    * Ensure your Azure ML workspace is configured.
    * Upload your model and configure the REST API endpoint in Azure ML.

4. Run the Jupyter notebook:
    * Open `Tesla (1).ipynb` in Jupyter or JupyterLab and execute each cell to train and evaluate the models.

5. Visualize results:
    * Use Power BI or other visualization tools to load the output data and track trend surges.

---

## **Usage**

Once the model is deployed, you can interact with the real-time API by sending requests to the **Azure-hosted endpoint**. This allows you to receive instant trend predictions for real-time decision-making.

---
## **Objective**

To build an accurate and explainable product trend forecasting model using machine learning that can provide valuable insights for market decision-making. The project implements three modeling strategies and selects the best based on AUC performance:

- ✅ **ARIMA**
- 🧪 **Prophet**
- 🔮 **LSTM**

---

## **Data Overview**

- **Total Entries:** 100,000+ data points
- **Time Span:** 12 months of product trend data

### **Categories of Features:**
- **product_id** - Product identifier
- **price** - Product price
- **quantity_sold** - Units sold
- **date** - Timestamp

---

## **Feature Engineering**

- 📅 **Aggregated temporal features:** mean, min, max, last over 12 months
- 🏷️ **One-hot encoded categorical columns** → multiple dummy variables
- 🧼 **Missing values handled based on type:**
  - Binary → 0
  - Categorical → Mode
  - Numeric → Mean

---

## **Model Training**

### **1️⃣ ARIMA**
- **Grid search** on:
  - p, d, q parameters
- **Performance Evaluation:** AUC, RMSE
- **Used for:** Short-term trend prediction

### **2️⃣ Prophet**
- **Parameters Tuning:** Seasonal, holidays, and trend change point detection
- **Performance Evaluation:** AUC, RMSE
- **Used for:** Long-term forecasting with seasonality

### **3️⃣ LSTM**
- **Model setup:** Tuned number of layers and neurons
- **Training process:** 32 epochs, batch size: 64
- **Performance Evaluation:** AUC, RMSE
- **Used for:** Predicting volatile trend patterns over time

---

## **Model Evaluation**

| **Model**   | **AUC (Test)** | **RMSE** | **Remarks**                |
|-------------|----------------|----------|----------------------------|
| **ARIMA**   | ✅ 0.80        | 5.2      | Good for short-term trends  |
| **Prophet** | ✅ 0.85        | 4.9      | Excellent for seasonality   |
| **LSTM**    | ✅ 0.92        | 4.2      | Best performance overall   |

---

## **What We Learned**

### **1. Forecasting High-Frequency Data is Challenging**
Working with high-frequency product trend data required careful preprocessing and feature engineering. Trends are often volatile, making it challenging to predict future shifts accurately. This reinforced the importance of **data quality** and **feature selection** in time series forecasting models.

### **2. LSTM Models Are Powerful for Sequence Prediction**
While traditional models like **ARIMA** and **Prophet** performed well, the **LSTM model** provided significantly better predictions due to its ability to capture long-term dependencies in time series data. The results reinforced the importance of **deep learning models** in handling sequential data, especially in **highly volatile environments** like product trends.

