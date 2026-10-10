Superstore Executive Sales & Performance Analytics

An end-to-end data analytics project designed to transform raw e-commerce order records into an interactive, portfolio-ready executive dashboard. This project demonstrates data engineering, SQL analytics, and visualization using Python, SQLite, and Power BI.

📌 Project Overview

This analytics project investigates a simulated Superstore dataset (~9,800 records) to identify key performance drivers, regional growth opportunities, customer segment distributions, and seasonal sales trends.

The workflow spans three core phases:

Data Cleaning & Feature Engineering: Processing raw sales data using Python (Pandas).

Relational Database Analytics: Querying operational metrics using SQL (SQLite).

Interactive BI Visualizations: Designing a modern, executive dark-mode ("Cyan-Glow") dashboard in Power BI.

🛠️ Tech Stack & Tools

Programming Language: Python 3.x

Data Manipulation: Pandas, NumPy

Database Engine: SQLite (In-Memory Database)

Visualization: Power BI Desktop

Dashboard Design: Custom Dark Theme (#0B0F19 background, #00E5FF high-contrast accents)

📊 Key Business Metrics (KPIs)

Total Sales: $2,430,247.55

Total Profit: $289,370

Total Orders: ~10,000

Total Customers: ~9,000

Profit Margin: ~12%

Avg Discount: ~11%

🚀 Repository Structure

├── Cleaned_Superstore_Sales.csv   # Preprocessed clean dataset
├── data_processing.py              # Python script for ETL and feature extraction
├── sql_analysis.py                # SQLite script executing business queries
├── Superstore_Dashboard.pbix       # Power BI Dashboard file
└── README.md                       # Project documentation


⚡ ETL & Feature Engineering (Python)

Key preprocessing steps performed:

Handled null values and inconsistent date formatting.

Calculated Shipping Days (Ship_Date - Order_Date).

Extracted temporal attributes: Order_Year, Order_Quarter, Order_Month, and Season (Spring, Summer, Autumn, Winter).

# Example Feature Engineering
df['Shipping_Days'] = (df['Ship_Date'] - df['Order_Date']).dt.days
df['Season'] = df['Order_Month'].map(month_to_season_dict)


🗄️ Business Queries & Analysis (SQL)

In-memory SQLite queries were executed to extract multi-dimensional insights:

Regional Sales & Profit Breakdown:

SELECT Region, 
       ROUND(SUM(Sales), 2) AS Total_Sales,
       ROUND(SUM(Profit), 2) AS Total_Profit
FROM superstore
GROUP BY Region
ORDER BY Total_Sales DESC;


Category & Segment Distribution: Analyzed discount impact across technology, furniture, and office supplies.

Seasonal Trend Evaluation: Identified revenue peaks across different operational quarters.

📈 Power BI Dashboard Highlights

KPI Header Cards: Displays real-time high-level summaries (Sales, Profit, Margin, Discounts, Shipping Days).

Segment Analysis: Horizontal bar chart comparing Consumer, Corporate, and Home Office categories.

Category Breakdown: Donut chart evaluating category contribution to total sales.

Regional & Seasonal Visuals: Bar and line charts tracking revenue shifts by geography and quarter.

Interactive Slicers: Top-level filters for dynamic drill-down by Order_Year and Region.

🏁 How to Run This Project

Clone the Repository:

git clone https://github.com/your-username/Sales-performance4.git


Run Python ETL:

python data_processing.py


Execute SQL Queries:

python sql_analysis.py


Open Dashboard:
Open Superstore_Dashboard.pbix in Power BI Desktop to explore the visual insights.

🤝 Author & Acknowledgments

Created by Saiful Islam as a professional portfolio demonstration of end-to-end business intelligence capabilities.
