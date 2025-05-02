🕒 Time Series-Based Anomaly Detection (Optional Enhancement)
In addition to the LSTM-based deep learning model, we integrate a classic time series anomaly detection approach to detect unexpected deviations in system log frequency or event occurrence over time. This serves as a complementary layer for systems where logs are timestamped and have temporal patterns.

Supported Time Series Models:
ARIMA (AutoRegressive Integrated Moving Average): Suitable for stationary time series after differencing.

Seasonal Decomposition + Z-Score Detection: Decomposes trend/seasonality from time series and detects outliers based on residuals.

Prophet (by Meta) (Optional): Useful for time series with strong seasonality, holidays, or irregular trends.

Workflow:
Aggregation:

Convert structured log data into time series format (e.g., count of events per minute/hour).

Group log templates over time using pandas.resample().

Model Training & Detection:

Train a time series model on historical (normal) log activity.

Forecast expected log behavior and compare with actual values.

Flag anomalies where the deviation exceeds a statistical threshold.

Integration with LSTM (optional):

Use time series models as a pre-filter or post-filter to validate LSTM-detected anomalies.

Ensemble decision-making can be implemented based on both methods.

Example (ARIMA + Log Count):
python
Copy
Edit
from statsmodels.tsa.arima.model import ARIMA
import pandas as pd

# Assume df['timestamp'] is already parsed
df.set_index('timestamp', inplace=True)
log_counts = df.resample('1min').size()

# Fit ARIMA
model = ARIMA(log_counts, order=(1, 1, 1))
model_fit = model.fit()

# Forecast and calculate residual
forecast = model_fit.predict(start=log_counts.index[0], end=log_counts.index[-1])
residuals = log_counts - forecast
anomalies = residuals[abs(residuals) > 3 * residuals.std()]  # Z-score threshold

print("Anomalies Detected:", anomalies)
📁 Updated Project Structure
text
Copy
Edit
├── data/
│   └── raw_logs/
│   └── parsed_logs/
│
├── drain_parser/
│   └── drain.py
│   └── regex_patterns.txt
│
├── models/
│   └── lstm_model.py
│   └── time_series_model.py  <-- NEW
│
├── utils/
│   └── preprocessing.py
│   └── visualization.py
│
├── notebooks/
│   └── exploratory_analysis.ipynb
│   └── time_series_anomaly_detection.ipynb  <-- NEW
🔍 Evaluation
For LSTM: Accuracy, Precision, Recall, F1.

For Time Series: Mean Absolute Error (MAE), Anomaly precision (how well time-based anomalies match real-world issues).

