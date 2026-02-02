# E-commerce Data Analysis Project

## Overview
This project analyzes an **E-commerce dataset** using Python, MySQL, Pandas, and visualization libraries.  
It covers **data ingestion, transformation, analysis, and visualization** to generate insights on sales, customers, products, and revenue trends.

## Dataset
The dataset includes the following CSV files:

- `customers.csv` — customer information (city, state, etc.)
- `orders.csv` — order information including timestamps and status
- `sellers.csv` — seller information
- `products.csv` — product details and categories
- `payments.csv` — payment information
- `order_items.csv` — products associated with each order

> **Note:** Some CSV files may contain missing values which are handled during data ingestion.

## Project Structure

project_folder/
│
├─ data/ # CSV files
├─ notebooks/ # Jupyter notebooks
├─ scripts/ # Python scripts for ETL and analysis
├─ README.md # Project documentation
└─ .gitignore # Ignored files and folders


## Steps Performed

### 1. Data Loading to MySQL
- Connected to MySQL using `mysql.connector`.
- Created tables for each CSV file dynamically with appropriate SQL types.
- Inserted data after handling missing values (`NaN → NULL`).

### 2. Data Cleaning & Transformation
- Cleaned column names by replacing spaces, hyphens, and dots with underscores.
- Handled missing values to prevent SQL errors.

### 3. Analysis & Insights

**Unique Customer Cities:**
```sql
SELECT DISTINCT customer_city FROM customers;
Orders Placed in 2017:

SELECT COUNT(order_id) FROM orders WHERE YEAR(order_purchase_timestamp) = 2017;
Top 10 Product Categories by Sales:

BED TABLE BATH: 1,712,553.67

HEALTH BEAUTY: 1,657,373.12

COMPUTER ACCESSORIES: 1,585,330.45

Percentage of Orders Paid in Installments: ~99.99%

Customer Count by State:

Visualized using bar chart for easy comparison.

Orders per Month (2018):

Calculated and visualized trends over months using Seaborn.

Average Products per Order by City:

Identified cities with highest average orders per customer.

Revenue Contribution by Category:

Top categories contributing the highest % of revenue plotted.

Correlation Between Product Price & Purchase Frequency:

Found weak negative correlation: -0.106.

Top 5 Sellers by Revenue:

Visualized using bar charts.

Customer Retention & YoY Growth:

Retention rate and year-over-year sales growth calculated.

Top 3 Customers by Yearly Spending:

Ranked customers using SQL dense_rank() window function.

Technologies Used
Python: pandas, numpy, matplotlib, seaborn

MySQL: Data storage, joins, aggregates, window functions

Jupyter Notebook: Interactive analysis and visualization

Git/GitHub: Version control

How to Run
Clone the repository:

git clone https://github.com/yourusername/repository.git
Install required Python packages:

pip install pandas mysql-connector-python matplotlib seaborn numpy
Place all CSV files inside data/ folder.

Update MySQL credentials in the Python script:

host='localhost', user='root', password='password', database='ecommerce'
Run the script:

python scripts/load_data_to_mysql.py
Open Jupyter notebooks to explore analysis and visualizations.

Visualizations
Sales by product category (bar chart)

Customers by state (bar chart)

Orders per month (bar chart)

Average orders per city (bar chart)

Revenue by category (bar chart)

Top sellers (bar chart)

Author
Sudip Shrestha
linked in : https://www.linkedin.com/in/sudip-shrestha-532622372/