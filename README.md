# stock_analysis_p1
Stock Analysis – ETL & Technical Analytics Project
Project Overview

This project focuses on analyzing historical stock market data to identify trading patterns, evaluate company performance, and generate technical and business insights. The project follows an ETL (Extract, Transform, Load) pipeline using Python, MySQL, and Data Visualization tools.

The main objective is to clean raw stock datasets, apply financial business rules, store cleaned data into a database, and build analytical dashboards for decision-making.

Tools & Technologies Used
Programming & Data Processing
->Python
->Pandas
->NumPy

Database
->MySQL
->SQLAlchemy
->MySQL Connector

Visualization
->Matplotlib

Development Environment
->Jupyter Notebook

Dataset Information
This project uses 3 separate stock datasets:
->MSFT Stock Data
->GOOG Stock Data
->AAPL Stock Data

Each dataset contains:
->Date
->Symbol
->Open Price
->Close Price
->High Price
->Low Price
->Volume
->Daily Return
->Trend

ETL Pipeline A

ETL Pipeline Architecture
Raw CSV Files
     ↓
Python ETL Processing
 - Duplicate Removal
 - Missing Value Treatment
 - Price Sanity Validation
 - Trend Classification
     ↓
Clean CSV Files
     ↓
MySQL Database Tables
     ↓
SQL Analytics Queries
     ↓
Matplotlib Dashboards

Data Cleaning & Business Rules Implemented  

1.Duplicate Handling
   Duplicates removed using:
     *Date
     *Symbol
Only first occurrence retained.  


2. Missing Value Treatment
Column	     Handling Method
close_price	Replaced with median close price per stock
volume	     Replaced with 0
high_price	Recalculated using max(open_price, close_price)
low_price	     Recalculated using min(open_price, close_price

3.Price Sanity Validation
Ensured:
*high_price ≥ open_price AND close_price
*low_price ≤ open_price AND close_price
Auto-corrected where violated.

4.Trend Classification
Condition	Trend
daily_return > 0	UP
daily_return < 0	DOWN
daily_return = 0	NO_CHANGE

--Technical Analysis Performed
*Daily Closing Price Trend Visualization
*Moving Average Calculation (7-Day, 30-Day)
*Volume vs Price Movement Analysis
*Volatility Identification


--Dashboard Interpretation
->Best Performing Stock by Average Return
This chart shows the average daily return for each stock. From the visualization, AAPL shows the highest average return compared to MSFT and GOOG. This indicates stronger overall performance during the dataset period.

<img width="505" height="415" alt="Screenshot (109)" src="https://github.com/user-attachments/assets/55879cbb-e198-4437-a0d0-541d41af3e0f" />

->Volume Spike Visualization
The volume spike graph highlights days where trading volume was unusually high. These spikes may indicate major market events, institutional trading activity, or strong investor interest on specific days.

<img width="885" height="450" alt="Screenshot (110)" src="https://github.com/user-attachments/assets/22002a9d-45e7-470f-ad4b-391311abaf39" />

-->UP vs DOWN Trend Ratio
This chart shows the number of days each stock moved upward versus downward. The results indicate that all three stocks have slightly more UP days than DOWN days, suggesting overall positive market movement during the dataset period.

<img width="515" height="409" alt="Screenshot (111)" src="https://github.com/user-attachments/assets/77d66e2f-2dff-4538-8684-3bede2a31859" />

--How to Run This Project
Step 1 — Install Requirements
pip install pandas numpy matplotlib sqlalchemy mysql-connector-python
Step 2 — Setup MySQL Database

--Create database:
CREATE DATABASE stock_analysis;
Step 3 — Update MySQL Connection

--Update username & password in notebook:
mysql+mysqlconnector://username:password@localhost:3306/stock_analysis

--Step 4 — Run Jupyter Notebook
Run cells sequentially:
Data Loading,Data Cleaning,Business Rule Implementation,Database Loading,Dashboard Generation

