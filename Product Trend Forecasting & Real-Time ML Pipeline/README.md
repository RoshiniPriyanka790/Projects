# **Product Trend Forecasting & Real-Time ML Pipeline (Azure ML, ARIMA, Prophet, LSTM)**

This repository contains a project focused on predicting **volatility patterns** in product trends using **time series forecasting** techniques. We applied multiple forecasting models, including **ARIMA**, **Prophet**, and **LSTM (Long Short-Term Memory)**, to capture high-frequency fluctuations and improve prediction accuracy. The goal of this project is to analyze product trends and forecast potential surges in market activity. By using these models, the project demonstrates how machine learning and traditional time series techniques can be leveraged to predict market or product performance.

The **LSTM model** is deployed as a **real-time REST API** for continuous predictions and alerting, providing instant metric predictions.

---

## **Key Features**
- **Time Series Forecasting Models**: ARIMA, Prophet, and LSTM for predicting product trend volatility.
- **Real-Time API Deployment**: LSTM model deployed using **Azure ML** as a REST API, providing instant predictions and alerts.
- **Model Retraining**: **Azure DevOps CI/CD** pipeline to automate the weekly retraining of the model to maintain production accuracy.
- **Data Visualization**: **Power BI** dashboards used to visualize trend spikes and forecast shifts for actionable insights.

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
    - Ensure your Azure ML workspace is configured.
    - Upload your model and configure the REST API endpoint in Azure ML.

4. Run the Jupyter notebook:
    - Open `Tesla (1).ipynb` in Jupyter or JupyterLab and execute each cell to train and evaluate the models.

5. Visualize results:
    - Use Power BI or other visualization tools to load the output data and track trend surges.

---

## **Usage**

Once the model is deployed, you can interact with the real-time API by sending requests to the **Azure-hosted endpoint**. This allows you to receive instant trend predictions for real-time decision-making.

For example, send a **POST** request with the input data:
```bash
curl -X POST -H "Content-Type: application/json" -d '{"data": [your_input_data]}' https://your-azure-endpoint
