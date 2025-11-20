# Chatbot-for-historical-insights-and-air-quality-predictions
This project develops an AI-powered system that combines a hybrid Prophet–LSTM model with an interactive chatbot to deliver historical insights and real-time air-quality predictions. It helps users analyze pollutant trends and access complex sensor data through simple natural-language queries.


---

# **AI-Powered Chatbot for Historical Insights and Air Quality Predictions**

This project integrates a **hybrid Prophet–LSTM forecasting model** with an **LLM-powered chatbot** to make air-quality data analysis more accessible, interactive, and insightful. Users can query historical pollution trends, generate visualizations, and access short-term predictions for key pollutants such as **PM2.5, PM10, and O₃** through a natural-language interface.

The system is designed for **researchers, students, policymakers, and the general public** who want an easy way to understand and explore air-quality patterns using AI.

---

## **✨ Features**

### **🔹 Air Quality Forecasting**

* Hybrid **Prophet + LSTM** model
* Predicts **PM2.5**, **PM10**, and **Ozone (O₃)**
* Captures long-term seasonality + short-term nonlinear patterns
* Trained on 7 years of CPCB Delhi sensor data (2017–2024)

### **🔹 LLM-Based Chatbot**

* Built using **LangGraph**
* Accepts natural-language questions
* Generates Python code internally to analyze data
* Returns plots, tables, comparisons, and insights
* Supports interactive exploration of historical sensor data

### **🔹 Interactive Visualizations**

* Time-series pollution trends
* Bar charts, comparisons across days/months/years
* Geographical mapping of sensor locations
* Clean UI for predictions and chatbot interactions

---

## **📁 Project Structure**

```
project/
│
├── data/                   
│   └── delhi_air_quality_2017_2024.csv
│
├── models/
│   ├── lstm_model_pm25.h5
│   ├── lstm_model_pm10.h5
│   ├── lstm_model_o3.h5
│   └── prophet_outputs/
│
├── src/
│   ├── preprocessing.py
│   ├── prophet_model.py
│   ├── lstm_model.py
│   ├── hybrid_model.py
│   ├── inference.py
│   └── chatbot/
│       ├── langgraph_flow.py
│       ├── code_generator.py
│       └── utils.py
│
├── results/
│   ├── pm25_predictions.png
│   ├── pm10_predictions.png
│   └── o3_predictions.png
│
├── app/
│   ├── dashboard.py
│   └── chatbot_ui.py
│
├── Final Report Updated.pdf
└── README.md
```

---

## **📊 Dataset Description**

* **Source:** CPCB Monitoring Station, IHBAS Dilshad Garden, Delhi
* **Duration:** 2017–2024
* **Pollutants:** PM2.5, PM10, O₃
* **Meteorological Features:**

  * Relative Humidity
  * Wind Speed
  * Wind Direction

These environmental parameters were combined to maximize forecasting accuracy.


---

## **🧹 Data Preprocessing**

* Missing values handled using `fillna()` and interpolation
* Time series continuity ensured
* Features normalized using **MinMaxScaler**
* Train/test splits generated for each pollutant-specific model

---

## **🧠 Model Architecture**

### **1. Prophet Component**

Captures:

* Long-term trends
* Seasonal patterns (daily/weekly/yearly)
* Holiday effects
* Handles outliers and missing timestamps gracefully

### **2. LSTM Component**

Learns:

* Short-term patterns
* Nonlinear behavior
* Residual sequences from Prophet

### **3. Hybrid Workflow**

1. Prophet predicts trend + seasonality
2. Residuals = Actual – Prophet Output
3. LSTM learns residual patterns
4. Final prediction = Prophet Forecast + LSTM Residual Prediction

---

## **🚀 How to Run the Project**

### **1. Install Requirements**

```
pip install -r requirements.txt
```

### **2. Run Forecasting Model**

```
python src/inference.py
```

### **3. Launch Chatbot**

```
python app/chatbot_ui.py
```

### **4. Launch Prediction Dashboard**

```
python app/dashboard.py
```

---

## **📈 Sample Outputs**

* Hybrid model predictions outperform standalone Prophet
* PM2.5, PM10, and O₃ forecasts visualized
* Chatbot-generated tables and charts


---

## **🛠️ Tech Stack**

**Machine Learning / Forecasting**

* Python
* Prophet
* TensorFlow / Keras (LSTM)

**Chatbot / LLM**

* LangGraph
* Custom code-generation pipeline

**Visualization**

* Matplotlib / Seaborn
* Plotly
* Interactive UI components

---

## **📝 License**

This project is licensed under the **Creative Commons Attribution–NonCommercial 4.0 International (CC BY-NC 4.0)** license.

---
