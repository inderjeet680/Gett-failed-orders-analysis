# 🚖 Gett Failed Orders Analysis 📉

## 📌 Overview
This project investigates **failed taxi orders** on the Gett platform (formerly *GetTaxi*), focusing on:
- Cancellation patterns  
- Rejection reasons  
- Geospatial clustering  

The goal is to diagnose why certain ride requests fail and uncover insights that can improve the rider–driver matching system.

---

## 📂 Dataset
- **Size:** 2.98 MB  
- **Contents:** Order-level information including:
  - Order status (success/failure)  
  - Cancellation reason  
  - Driver assignment status  
  - Estimated Time of Arrival (ETA)  
  - Timestamp of order  
  - Geolocation data  

### Data Description
#### `data_orders.csv`
- `order_datetime` → Time of the order  
- `origin_longitude` → Longitude of pickup  
- `origin_latitude` → Latitude of pickup  
- `m_order_eta` → Estimated time before arrival  
- `order_gk` → Order number  
- `order_status_key` → Status codes:  
  - `4` → Cancelled by client  
  - `9` → Cancelled by system (reject)  
- `is_driver_assigned_key` → Driver assignment flag  
- `cancellation_time_in_seconds` → Time elapsed before cancellation  

#### `data_offers.csv`
- `order_gk` → Order number (linked to `data_orders`)  
- `offer_id` → Offer ID  

---

## ✅ Tasks Completed
1. **Failure Reason Distribution**  
   - Categorized failed orders:  
     - Cancellations before driver assignment  
     - Cancellations after driver assignment  
     - System rejections  
   - Identified dominant failure category.

2. **Hourly Failure Trends**  
   - Plotted failures by hour of day.  
   - Highlighted peak hours with abnormal failure proportions.  
   - Discussed possible causes (rush hours, driver shortages).

3. **Cancellation Timing**  
   - Compared average cancellation time with/without driver assignment.  
   - Removed outliers for clarity.  
   - Analyzed hourly cancellation trends.

4. **ETA Distribution**  
   - Plotted average ETA by hour.  
   - Explained patterns in relation to traffic congestion and driver density.

5. **Geospatial Hex Clustering (Bonus)**  
   - Applied **H3** hexagonal grid system.  
   - Visualized with **Folium** maps.  
   - Calculated hexes containing 80% of orders.  
   - Highlighted hotspots of failed orders.

---

## 🛠 Tech Stack
- **Python**  
- **Pandas** → Data wrangling  
- **Matplotlib / Seaborn** → Visualization  
- **Folium** → Interactive maps  
- **H3** → Geospatial hex clustering  

---

## 🔍 Key Insights
- **Dominant failure type:** Cancellations before driver assignment.  
- **Peak failure hours:** Align with rush-hour demand mismatches.  
- **ETA distribution:** Reflects traffic congestion and driver density.  
- **Geospatial clustering:** Reveals concentrated hotspots of failed orders.  

---

## 📎 Next Steps
- Investigate driver supply vs. demand imbalance.  
- Explore predictive modeling for cancellation likelihood.  
- Recommend operational improvements for peak hours.  
