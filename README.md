### 🕒 Time Series-Based Anomaly Detection (New)

Alongside the LSTM model, this project integrates a time series-based approach to detect anomalies in log event frequency over time. This method is particularly effective for identifying sudden spikes or drops in log activity.

#### ➤ Workflow:
- Convert structured logs into a time series format (e.g., event counts per minute).
- Apply statistical models such as ARIMA or Z-score-based residual analysis.
- Detect anomalies based on significant deviations from expected trends.

#### ➤ Use Cases:
- Real-time anomaly alerts based on log volume patterns.
- Lightweight fallback when deep learning is not feasible.
- Supports ensemble decisions with the LSTM model.

- # 🚨 Log Anomaly Detection using Deep Learning

This project combines the Drain log parsing algorithm with deep learning (LSTM) and statistical time series models to detect anomalies in system logs. It helps identify abnormal patterns, sudden spikes, or deviations in system behavior and alerts the system administrator or root user.

---

## 🧠 Introduction

This project follows a hybrid three-step approach:

1. **Drain Log Parsing**  
   Parses raw logs into structured templates using a parse tree based on log length and token similarity.

2. **LSTM-Based Anomaly Detection**  
   A deep learning model trained on normal sequences of logs to detect deviations.

3. **Time Series-Based Anomaly Detection**  
   Uses statistical models like ARIMA or Z-score analysis on log volume over time to detect frequency-based anomalies.

---

## ✅ How to Use This Repo (Step-by-Step)

### 🔁 1. Clone the Repository

```bash
git clone https://github.com/DepressedSage/Log-Anomaly-Detection-using-Deep-Learning.git
cd Log-Anomaly-Detection-using-Deep-Learning


#### ➤ Added Components:
- `models/time_series_model.py` for time series logic.
- `notebooks/time_series_anomaly_detection.ipynb` for exploratory analysis.

This hybrid approach enhances accuracy and interpretability in production monitoring environments.
