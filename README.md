# Time-Series Forecasting for System Monitoring


## 🎯 Project Overview

**A complete real-time server monitoring and forecasting system** that combines modern DevOps tools with machine learning to predict system resource usage. This project demonstrates end-to-end MLOps practices with automated data collection, preprocessing, model training, and interactive visualization.

### 🔍 What This Project Does

- **📊 Real-time Monitoring**: Continuously collects CPU and memory metrics from Linux servers
- **🤖 ML Forecasting**: Uses SARIMA models to predict system resource usage 4 hours into the future
- **📈 Interactive Dashboards**: Beautiful Streamlit UI for forecast visualization and Grafana for real-time monitoring
- **🔬 Experiment Tracking**: MLflow integration for model versioning and performance tracking
- **🐳 Containerized Deployment**: Complete Docker stack with 7 integrated services

### 🎪 Tech Stack

![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=flat&logo=grafana&logoColor=white)
![InfluxDB](https://img.shields.io/badge/InfluxDB-22ADF6?style=flat&logo=influxdb&logoColor=white)
![MLflow](https://img.shields.io/badge/MLflow-0194E2?style=flat&logo=mlflow&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat&logo=streamlit&logoColor=white)

---



## 🏗️ System Architecture






### 🔄 Service Stack

| **Layer** | **Service** | **Purpose** |
|-----------|-------------|-------------|
| **📊 Visualization** | Streamlit | Interactive ML Dashboard |
| **📈 Monitoring** | Grafana | Real-time System Dashboards |
| **🔬 ML Ops** | MLflow | Experiment Tracking & Model Registry |
| **💾 Storage** | InfluxDB | Time-series Database (ML Training) |
| **📊 Metrics** | Prometheus | Metrics Collection & Querying |
| **🔧 Collection** | Telegraf | Data Ingestion Agent |
| **📡 Exporter** | Node Exporter | System Metrics Endpoint |

---

## 🤖 Machine Learning Pipeline

### 📈 SARIMA Forecasting

Our ML pipeline uses **Seasonal ARIMA (SARIMA)** models optimized for system metrics:

- **🎯 Target Metrics**: CPU & Memory usage percentages
- **⏰ Forecast Horizon**: Next 4 hours (48 steps at 5-minute intervals)
- **🔄 Seasonality**: 1-hour cycles (12 periods × 5 minutes)
- **📊 Model Selection**: Automated parameter optimization with AIC scoring

### 🔄 Pipeline Flow


```bash
Linux System/Windows system → Node Exporter/Windows Exporter → Prometheus (15s intervals) → Grafana Dashboards -> Telegraf -> InfluxDB 
```

### 📁 Pipeline Components

| **Script** | **Function** | **Output** |
|------------|--------------|------------|
| `src/main.py` | 🚀 **Pipeline Orchestrator** | Runs complete workflow |
| `src/ingestion.py` | 📥 **Data Collection** | Raw metrics from InfluxDB |
| `src/pre_processing.py` | 🧹 **Data Cleaning** | Preprocessed time series |
| `src/model_train.py` | 🤖 **Model Training** | SARIMA models + forecasts |
| `src/model_inference.py` | 🔮 **Predictions** | Latest model predictions |

---

## ✨ Key Features

### 🎨 Interactive Streamlit Dashboard

- **📊 Real-time Metrics**: Current CPU/Memory usage with beautiful gradient cards
- **📈 Forecast Charts**: Interactive Plotly visualizations with historical vs predicted data
- **🔮 4-Hour Predictions**: Average forecast values across the prediction horizon
- **📱 Responsive Design**: Modern UI with tabbed interface for different analyses

### 📊 Monitoring & Alerting

- **🔍 Grafana Dashboards**: Pre-configured system monitoring with Node Exporter metrics
- **⚡ Real-time Updates**: 15-second metric collection intervals
- **📈 Historical Analysis**: Long-term trend analysis and pattern recognition

### 🔬 MLOps Integration

- **📝 Experiment Tracking**: MLflow logging of model parameters, metrics, and artifacts
- **🏷️ Model Versioning**: Automatic model registration and version management
- **📊 Performance Metrics**: AIC/BIC scoring and forecast validation
- **🔄 Automated Retraining**: Easy pipeline re-execution for model updates

### 🐳 Production-Ready Deployment

- **📦 Containerized Services**: Complete Docker Compose stack
- **🔒 Security**: Proper user permissions and environment variable management
- **📈 Scalability**: Modular architecture for easy extension
- **🛠️ Maintenance**: Health checks and automated restarts

---

