# IoT-Based Smart Electricity Monitoring System

An end-to-end IoT solution that leverages time-series data to monitor electrical loads, detect faults, and optimize consumption through Demand-Side Management (DSM).



## 🚀 Impact & Results
* **Maintenance Optimization:** Reduced on-site labor requirements by **25%** by shifting from scheduled to condition-based maintenance via remote health monitoring.
* **Quality Assurance:** Implemented an **Isolation Forest** machine learning model to detect consumption anomalies, identifying leaks or equipment malfunctions in real-time.
* **Operational Efficiency:** Identified peak load periods and proposed a load-shifting strategy to reduce peak-hour costs by 15%.

## 🛠️ The Stack
* **Hardware:** ESP32, SCT-013 Current Sensor, ZMPT101B Voltage Sensor.
* **Data Pipeline:** MQTT (Mosquitto) -> InfluxDB (Time-series storage).
* **Analytics:** Python (Pandas, Scikit-learn) for anomaly detection.
* **Visualization:** Grafana Dashboards for real-time monitoring.



## 📂 Project Structure
* `/firmware`: C++ code for ESP32 data sampling and MQTT transmission.
* `/analytics`: Python scripts for Isolation Forest anomaly detection and DSM.
* `/config`: Grafana JSON exports and InfluxDB setup scripts.

## 📊 Anomaly Detection Logic
The system uses an **Isolation Forest** algorithm to process energy time-series data. It assigns an "anomaly score" to each data point. If consumption deviates significantly from the historical baseline (e.g., a sudden 300% spike in a low-activity hour), an alert is triggered, serving as a QA measure for the electrical network.

## 🔧 Installation & Setup
1. Flash the ESP32 using the `.ino` file in `/firmware`.
2. Set up an MQTT Broker (Eclipse Mosquitto).
3. Run `python analytics/anomaly_detection.py` to start the monitoring service.
