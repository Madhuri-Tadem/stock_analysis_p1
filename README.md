# stock_analysis_p1
📊 Stock Analysis – ETL & Technical Analytics Project
📌 Project Overview

This project focuses on analyzing historical stock market data to identify trading patterns, evaluate company performance, and generate technical and business insights. The project follows an ETL (Extract, Transform, Load) pipeline using Python, MySQL, and Data Visualization tools.

The main objective is to clean raw stock datasets, apply financial business rules, store cleaned data into a database, and build analytical dashboards for decision-making.

🛠️ Tools & Technologies Used
Programming & Data Processing
->Python
->Pandas
-1.NumPy

Database
-1.MySQL
->SQLAlchemy
->MySQL Connector

Visualization
->Matplotlib

Development Environment
->Jupyter Notebook

🔄 ETL Pipeline Architecture
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

🚀 How to Run This Project
Step 1 — Install Requirements
pip install pandas numpy matplotlib sqlalchemy mysql-connector-python
Step 2 — Setup MySQL Database

Create database:
CREATE DATABASE stock_analysis;
Step 3 — Update MySQL Connection

Update username & password in notebook:
mysql+mysqlconnector://username:password@localhost:3306/stock_analysis

Step 4 — Run Jupyter Noteboo
Run cells sequentially:
Data Loading,Data Cleaning,Business Rule Implementation,Database Loading,Dashboard Generation
