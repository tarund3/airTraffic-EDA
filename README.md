# airTraffic-EDA
The main objective of this project is to analyze flight patterns using K-Means clustering and extract meaningful insights from flight path data.
**Exploratory Data Analysis (EDA) on Flight Path Clustering**

## **1. Introduction**
This analysis aims to explore flight path data using K-Means clustering. By segmenting flights based on location (longitude, latitude), altitude, and speed, we can identify common flight patterns, detect anomalies, and analyze airspace utilization.

## **2. Data Overview**
- **Dataset:** Aircraft flight data containing flight details such as position, altitude, speed, and timestamp.
- **Key Features Used for Clustering:**
  - `long` (Longitude)
  - `lat` (Latitude)
  - `alt` (Altitude - normalized)
  - `mph` (Speed - normalized)

## **3. K-Means Clustering Analysis**
- ![image](https://github.com/user-attachments/assets/329e3222-b88d-403e-b436-24a8ff34be69)
- **Optimal Number of Clusters (k):** The Elbow Method was used to determine that `k=4` is the best choice for segmenting flight paths.
- **Cluster Assignments:**
  - Each flight was assigned to one of four clusters based on spatial and altitude characteristics.
  
### **Cluster Characteristics Summary:**
| Cluster | Avg. Altitude | Avg. Speed | Characteristics |
|---------|--------------|------------|-----------------|
| 0       | 0.203       | 0.740      | Mid-altitude flights, common regional jets |
| 1       | 0.126       | 0.664      | Low-altitude, low-speed flights, possibly private or local aircraft |
| 2       | 0.241       | 0.768      | High-altitude, high-speed flights, likely commercial jets |
| 3       | 0.239       | 0.766      | Similar to cluster 2, possibly international or military routes |

## **4. Cluster Visualizations**
### **Flight Path Distribution**
- ![image](https://github.com/user-attachments/assets/fb5f32c6-cbdf-4d3a-a9b1-6c7d72a0a87d)
- **2D Scatter Plot:** Shows that flight paths are well-separated based on longitude and latitude.
- ![image](https://github.com/user-attachments/assets/bcac25e9-8a10-46cc-a907-b70b3a6a813c)
- **3D Scatter Plot:** Highlights altitude variations among clusters, indicating different flight categories.

### **Altitude vs. Speed by Cluster**
- **Observations:**
  - ![image](https://github.com/user-attachments/assets/5d93b9ab-6f6c-4181-9689-6b43bd1013f7)
  - Low-altitude flights tend to have lower speeds.
  - High-altitude flights maintain consistent cruising speeds.
  - Some overlap exists, possibly due to mixed air traffic in certain areas.

### **Cluster Density Analysis**
- ![image](https://github.com/user-attachments/assets/8bc3066d-8f38-411a-a326-c9a8ea523b24)
- **Cluster 1 (low altitude, low speed) has the highest number of flights**, followed by Cluster 0.
- Clusters 2 and 3 have fewer flights, suggesting these could be specialized routes (e.g., military, private charters).

## **5. Time-Based Flight Distribution**
- **Hourly Flight Activity:**
  - ![image](https://github.com/user-attachments/assets/4b4d5121-4e7a-4017-89dc-d7ea540b43fa)
  - Peak flight hours occur between **8 AM - 8 PM**, likely corresponding to commercial air traffic.
  - **Clusters 2 & 3 (high-altitude flights) dominate peak hours**, aligning with major flight schedules.
  - **Cluster 1 (low-altitude flights) shows more activity at night**, potentially indicating private or military flights.

## **6. Anomaly Detection**
- ![image](https://github.com/user-attachments/assets/6d422595-89ce-470e-9874-634db5dffb5d)
- **Outliers detected based on distance from cluster centers.**
- **Potential causes:**
  - Emergency flight diversions
  - Military test flights
  - Unusual air traffic patterns due to weather disruptions

## **7. Conclusion & Next Steps**
- The clustering approach successfully segmented flights into meaningful groups based on **altitude, speed, and location**.
- Further analysis could involve:
  - **Comparing clusters with real-world flight schedules** to verify insights.
  - **Studying anomalies in more detail** to understand the causes of flight deviations.
  - **Integrating weather and air traffic control data** for a more comprehensive analysis.

By leveraging clustering techniques, we can better understand flight behaviors and airspace utilization, making this analysis useful for aviation analytics, air traffic management, and security monitoring.
