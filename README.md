# 🚗⚡ EV Ride-Sharing Analytics – Power BI | SQL | Python

A full-stack end-to-end data analytics project analyzing customer behavior, ride patterns, driver performance, EV fleet usage, charging station efficiency, and revenue insights for an EV Ride-Sharing business.

📌 Project Overview

This project analyzes 5,000+ rides, 2,000 customers, 300 drivers, 300 vehicles, and charging station performance using:

🔹 Python (Pandas) → Data Cleaning
🔹 SQL Server → Data Modeling & Analysis
🔹 Power BI → Interactive Dashboard
🔹 DAX → Business Metrics Calculation

This end-to-end pipeline simulates real EV mobility operations (similar to BluSmart, Ola Electric, Uber Green).

📊 Dashboard Highlights

Page 1 – Executive Summary

Total Rides, Revenue, Customers, Drivers
Monthly Ride Trend
Revenue by City
Peak Ride Hours

Page 2 – Customer Insights

Signup Trends
Age Groups
Gender Split
Top Active Customers
Avg Fare per Customer

Page 3 – Driver Performance

Rating Distribution
Top Drivers by Rides
Drivers by City
Tips Earned Leaderboard

Page 4 – Ride Analytics

Ride Distance Bins
Ride Duration
Fare vs Distance
Ride Trends by Hour/Month

Page 5 – Vehicle Analytics

Vehicle Types
Brand/Model Distribution
Avg Range (km)
Vehicles Used per Month

Page 6 – Charging Station Analytics

Station Uptime %
Charging Sessions
Cities with Highest Load
Cost per kWh Comparison

Page 7 – Revenue / Financial Insights

Monthly Revenue
Payment Mode Split
Fare Trends
Rating vs Fare Correlation
Revenue by Vehicle Type

🛠️ Technologies Used
Tool	Purpose
Python (Pandas)	Cleaning CSV data, feature engineering
SQL Server	Data modeling, joins, aggregations, business logic
Power BI	Dashboard creation & DAX calculations
DAX	KPIs, time-intelligence, metrics
Excel / CSV	Raw dataset storage
🗂️ Dataset Structure

The dataset contains the following tables:

Table	Rows	Description
rides	5000	Ride-level metrics
customers	2000	Customer demographics
drivers	300	Driver details & ratings
vehicles	300	EV fleet info
charging_stations	50	Charging station uptime & cost
payments	5000	Fares, tips, payment mode

📈 Key Business KPIs
📌 Rides & Operations

Total Rides
Avg Ride Distance (4.98 km)
Avg Ride Duration (22.5 min)

📌 Drivers

Avg Driver Rating (4.57)
Rides per Driver per Month

📌 Customers

2000 Registered Users
Age Group & City Behavior

📌 Revenue

Total Revenue
Avg Revenue per Driver
Tips Earned

🧩 Data Model (Star Schema)

✔ rides (Fact Table)
✔ customers (Dimension)
✔ drivers (Dimension)
✔ vehicles (Dimension)
✔ charging_stations (Dimension)
✔ payments (Fact)
✔ Date Table (Dimension)

Relationships created using driver_id, customer_id, payment_id, vehicle_id, and city bridge for charging.

🧪 SQL Analysis Samples
-- Total revenue per month
SELECT MONTH(start_time) AS Month,
       SUM(amount) AS Total_Revenue
FROM rides r
JOIN payments p ON r.ride_id = p.ride_id
GROUP BY MONTH(start_time)
ORDER BY Month;

-- Top 10 drivers by ride count
SELECT TOP 10 d.name, COUNT(*) AS Total_Rides
FROM drivers d
JOIN rides r ON d.driver_id = r.driver_id
GROUP BY d.name
ORDER BY Total_Rides DESC;

📁 Folder Structure
📦 EV-Ride-Sharing-Analytics
 ┣ 📂 data_raw
 ┣ 📂 data_processed
 ┣ 📂 SQL
 ┣ 📂 python
 ┣ 📂 pbix
 ┣ 📄 README.md

🏁 Conclusion

This project simulates a real-world EV ride-hailing business with end-to-end analytics from raw data → cleaned → modeled → dashboards.
It demonstrates strong skills in:


✔ Data Analysis
✔ BI Reporting
✔ Python + SQL + DAX
