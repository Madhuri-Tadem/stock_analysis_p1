# stock_analysis_p1
## Stock Analysis – ETL and Technical Analytics Project

---

## Project Overview

- This project analyzes historical stock market data to identify trading patterns and evaluate company performance.
- It follows a complete ETL (Extract, Transform, Load) pipeline using Python, MySQL, and visualization tools.
- The objective is to clean raw stock datasets, apply financial business rules, store processed data into a database, and build dashboards for decision-making.
- The project demonstrates practical data engineering combined with financial analytics.

---

## Tools and Technologies Used

### Programming and Data Processing
- Python
- Pandas
- NumPy

### Database
- MySQL
- SQLAlchemy
- MySQL Connector

### Visualization
- Matplotlib

### Development Environment
- Jupyter Notebook

---

## Dataset Information

- The project uses three separate stock datasets:
  - MSFT Stock Data
  - GOOG Stock Data
  - AAPL Stock Data

- Each dataset contains:
  - Date
  - Symbol
  - Open Price
  - Close Price
  - High Price
  - Low Price
  - Volume
  - Daily Return
  - Trend

- Each dataset was processed independently to maintain modular and scalable analysis.

---

## ETL Pipeline Architecture

- Raw CSV Files
- Python ETL Processing
  - Duplicate Removal
  - Missing Value Treatment
  - Price Sanity Validation
  - Trend Classification
- Cleaned Data
- MySQL Database Tables
- SQL Analytical Queries
- Matplotlib Dashboards

---

## Data Cleaning and Business Rules Implemented

### 1. Duplicate Handling

- Duplicates were removed using:
  - Date
  - Symbol
- Only the first occurrence was retained.

### 2. Missing Value Treatment

- close_price
  - Replaced with median close price per stock
- volume
  - Replaced with 0
- high_price
  - Recalculated using max(open_price, close_price)
- low_price
  - Recalculated using min(open_price, close_price)

### 3. Price Sanity Validation

- Ensured:
  - high_price ≥ open_price and close_price
  - low_price ≤ open_price and close_price
- Any violations were automatically corrected.

### 4. Trend Classification

- daily_return > 0 → UP
- daily_return < 0 → DOWN
- daily_return = 0 → NO_CHANGE

---

## Technical Analysis Performed

- Daily Closing Price Trend Visualization
- Moving Average Calculation (7 Day and 30 Day)
- Volume vs Price Movement Analysis
- Volatility Identification

---

## Dashboards and Business Interpretation

### Best Performing Stock by Average Return
<img width="505" height="415" alt="Screenshot (109)" src="https://github.com/user-attachments/assets/55879cbb-e198-4437-a0d0-541d41af3e0f" />

- Compares average daily return of MSFT, GOOG, and AAPL.
- AAPL shows the highest average return among the three stocks.
- MSFT and GOOG show stable but slightly lower performance.

Business Insight:
- AAPL demonstrated stronger growth during the dataset period.
- Return performance should also be evaluated along with volatility and risk.

### Volume Spike Detection

<img width="885" height="450" alt="Screenshot (110)" src="https://github.com/user-attachments/assets/22002a9d-45e7-470f-ad4b-391311abaf39" />

- Identifies abnormal trading volume using percentile-based threshold logic.
- Days exceeding the threshold are considered abnormal spikes.

Possible reasons:
- Company announcements
- Institutional buying or selling
- Market news
- Economic events

Business Insight:
- Volume spikes help detect unusual market activity and potential trend reversals.

### UP vs DOWN Trend Ratio

<img width="515" height="409" alt="Screenshot (111)" src="https://github.com/user-attachments/assets/77d66e2f-2dff-4538-8684-3bede2a31859" />

- Shows count of UP, DOWN, and NO_CHANGE days for each stock.
- All three stocks show slightly more UP days than DOWN days.

Business Insight:
- A higher number of UP days indicates positive market sentiment.
- Helps evaluate stock stability and long-term behavior.

---

## Database Implementation

- Cleaned datasets were loaded into MySQL using SQLAlchemy.
- Used the to_sql() method for table creation.

Tables created:
- msft_stock_clean
- goog_stock_clean
- aapl_stock_clean

- SQL queries were used to generate business metrics and summary analytics.

---

## How to Run the Project

Step 1: Install Required Libraries

pip install pandas numpy matplotlib sqlalchemy mysql-connector-python

Step 2: Create MySQL Database

CREATE DATABASE stock_analysis;

Step 3: Update Database Connection

mysql+mysqlconnector://username:password@localhost:3306/stock_analysis

Step 4: Run Jupyter Notebook

Run cells in this order:
- Data Loading
- Data Cleaning
- Business Rule Implementation
- Database Loading
- Dashboard Generation

---

## Key Learnings

- Designing a real-world ETL workflow
- Applying financial data validation rules
- Handling structured datasets efficiently
- Writing analytical SQL queries
- Building dashboard-ready datasets

---

## Conclusion

- This project demonstrates an end-to-end ETL and analytics workflow using financial data.
- It combines data cleaning, database integration, technical analysis, and visualization.
- The modular dataset approach ensures scalability and structured analysis.


