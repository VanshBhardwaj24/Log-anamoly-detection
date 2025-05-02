Log-Anomaly-Detection-using-Deep-Learning
This project combines the power of the Drain algorithm for log parsing with Long Short-Term Memory (LSTM) neural networks and time series models for anomaly detection in system logs. The Drain algorithm preprocesses and compiles system logs into structured event templates, which are then used as input for both LSTM and statistical time series-based models. These models detect anomalies in the system execution and report them to the root user or system administrator.

🧠 Introduction
This project focuses on building an efficient system for detecting anomalies in system logs using a three-step process:

Drain Log Parsing: Employing the Drain algorithm, a fixed-depth tree-based online log parsing method. This algorithm preprocesses raw log messages using domain-specific regular expressions, compiles them into event templates, and structures them in a parse tree.

LSTM-based Anomaly Detection: Using deep learning to learn patterns from structured sequences of log events and detect deviations.

Time Series-Based Anomaly Detection: Applying statistical models to detect abnormal spikes or drops in log event frequency over time.

🚀 Getting Started
Clone this repository:

sh
Copy
Edit
git clone https://github.com/DepressedSage/Log-Anomaly-Detection-using-Deep-Learning.git
Navigate to the project directory:

sh
Copy
Edit
cd Log-Anomaly-Detection-using-Deep-Learning
Install the required dependencies:

sh
Copy
Edit
pip install numpy pandas keras tensorflow statsmodels matplotlib
⚙️ Prerequisites
Ensure you have the following dependencies:

Python >= 3.6

NumPy

Pandas

Keras

TensorFlow

Statsmodels

Matplotlib (for time series visualization)

🧩 Usage
1. Drain Log Parsing:
Preprocess raw log messages using domain-specific regular expressions to remove variable components.

Parse messages into structured templates using a parse tree based on length and token similarity.

2. LSTM-based Anomaly Detection:
Input structured log data into an LSTM model trained on normal log sequences.

Detect and flag sequences that deviate significantly from learned patterns.

3. Time Series-Based Anomaly Detection (New):
Convert logs into time series (e.g., event count per minute/hour).

Train a statistical model like ARIMA or use Z-score detection on residuals.

Detect anomalies based on abnormal frequency patterns.

🔄 Project Structure and Flow


📁 Project Structure
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
│   └── time_series_model.py  # NEW
│
├── utils/
│   └── preprocessing.py
│   └── visualization.py
│
├── notebooks/
│   └── exploratory_analysis.ipynb
│   └── time_series_anomaly_detection.ipynb  # NEW
📊 Results
LSTM: Accuracy, Precision, Recall, and F1-score metrics reflect how well the model detects anomalous log sequences.

Time Series: Anomalies are detected based on deviations in event frequency using residual analysis and statistical thresholds (e.g., Z-score or confidence intervals).

🤝 Contributing
Contributions are welcome! Feel free to fork this repo, improve it, and submit a pull request.

📄 License
This project is licensed under the MIT License.

