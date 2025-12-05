# Metro Tunnel Worker Safety AI System

This project simulates an AI-assisted safety monitoring system for metro tunnel workers by fusing computer vision–style PPE flags with environmental sensor data and automated evacuation planning.

## Overview

The system focuses on four core capabilities:

- Synthetic data generation for underground tunnel environments  
- Anomaly detection on multi-sensor time-series data  
- Risk scoring and worker safety classification  
- Evacuation path planning using grid-based A* search  

All experiments are implemented in the `metro_work1-1.ipynb` notebook. [file:22]

## Methodology

1. **Data Simulation**  
   Generated synthetic time-series data for 10 workers, including gas concentration, vibration level, temperature, and worker coordinates to emulate underground tunnel conditions and hazard scenarios. [file:22]

2. **Anomaly Detection**  
   Applied Isolation Forest–based anomaly detection on gas and vibration streams to flag abnormal readings that may indicate leaks or structural stress, adding boolean anomaly indicators (`sensor_gas_anomaly`, `sensor_vibration_anomaly`). [file:22]

3. **Risk Logic Engine**  
   Designed a risk-scoring pipeline that fuses sensor anomaly flags with PPE/compliance flags (e.g., helmet/vest status in a real deployment) to compute a numerical `risk_score` and assign each worker a categorical `risk_level` of **Safe**, **Moderate**, or **High**. [file:22]

4. **Pathfinding & Evacuation Planning**  
   Modeled the tunnel as a grid graph and used the A* pathfinding algorithm to compute the shortest evacuation route from each worker’s position to the nearest safe exit, recording an `evacuation_path_length` per worker. [file:22]

## Key Results

- **Scenario Coverage**  
  Simulated 10 workers across multiple time steps, producing labeled records with time, worker ID, coordinates, gas, vibration, temperature, anomaly flags, risk score, and risk level. [file:22]

- **Risk & Evacuation Outcomes**  
  Identified **3 workers** requiring evacuation and computed individualized shortest paths (up to **94 units** in path length). The experiments surfaced **3 PPE violations**, **50 gas anomalies**, **50 vibration anomalies**, and **1 smoke incident**, illustrating how fused sensor and compliance signals can drive automated, risk-based evacuation planning. [file:22]

## Repository Structure

- `metro_work1-1.ipynb` – Main experimentation notebook containing data simulation, anomaly detection, risk logic, and A* pathfinding workflows. [file:22]

## Future Work

- **Real-Time Visualization:** Build an interactive dashboard (e.g., Streamlit/Plotly) to visualize worker locations, anomaly events, and evacuation paths in real time.  
- **Edge Deployment:** Optimize models and pipelines for NVIDIA Jetson / Raspberry Pi to enable low-latency, on-site processing in tunnel environments.  
- **Hardware Integration:** Integrate the system with physical IoT sensor nodes (e.g., ESP32) to stream live gas, vibration, temperature, and PPE-status data into the risk engine.  
- **Thermal Imaging:** Incorporate thermal vision to maintain reliable worker detection and localization under low-visibility conditions such as smoke or dust.  


