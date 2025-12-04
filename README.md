# Safety AI Assistance for Metro Workers

## Project Overview
Tunnel construction for metro projects exposes workers to critical hazards such as gas leaks, structural instability, and poor visibility. This project, **Tunnel Twin AI**, integrates Computer Vision for PPE detection, Sensor Anomaly Detection for environmental hazards, and A* pathfinding for evacuation simulation into a unified real-time risk assessment platform.

## Objectives
*   **PPE Compliance:** Detect personal protective equipment (helmets, vests) using YOLOv8.
*   **Hazard Identification:** Identify anomalous conditions like gas leaks and vibrations using Isolation Forest.
*   **Risk Scoring:** Compute real-time risk scores by fusing visual and sensor data.
*   **Evacuation Planning:** Simulate optimal evacuation routes using the A* algorithm.
*   **Visualization:** Provide supervisors with real-time 3D dashboards of worker safety status.

## Tech Stack
*   **Core:** Python, NumPy, Pandas
*   **AI/ML:** YOLOv8 (Object Detection), Isolation Forest (Anomaly Detection), Scikit-learn
*   **Simulation & Logic:** A* Algorithm (Pathfinding), NetworkX
*   **Visualization:** Plotly, Matplotlib

## Methodology
1.  **Data Simulation:** Generated synthetic datasets for environmental variables (Gas, Vibration, Temperature) and worker coordinates.
2.  **Anomaly Detection:** Implemented Isolation Forest to detect statistical outliers in sensor streams (simulating leaks or structural stress).
3.  **Risk Logic Engine:** Developed a fusion algorithm that categorizes safety status (Safe/Moderate/High) based on combined CV flags and sensor anomalies.
4.  **Pathfinding:** Modeled the tunnel layout as a grid graph and utilized the A* algorithm to compute the shortest safe exit path for workers in high-risk zones.

## Key Results
*   **Integrated Monitoring:** Successfully combined computer vision and sensor data streams for holistic safety analysis.
*   **Automated Risk Assessment:** Real-time classification of worker risk levels based on environmental factors.
*   **Dynamic Evacuation:** Automated generation of safe exit routes during simulated hazard events.
*   **3D Visualization:** Developed a functional prototype dashboard for spatial monitoring of worker locations and hazard zones.

## Future Scope
*   **Edge Deployment:** Optimization of models for NVIDIA Jetson/Raspberry Pi for low-latency onsite processing.
*   **Hardware Integration:** Integration with physical IoT sensor nodes (ESP32) for live data telemetry.
*   **Thermal Imaging:** Incorporation of thermal vision for worker detection in low-visibility smoke conditions.

