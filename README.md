### Project Description: Sales_Insights

#### Objective
The "Sales_Insights" project aims to provide a comprehensive analysis of sales data, leveraging the power of MySQL and Power BI to transform raw data into actionable insights. The goal is to explore, clean, and visualize the data to support data-driven decision-making processes.

#### Data Exploration and Analysis
1. **Data Exploration in MySQL:**
   - **Data Ingestion:** Initially, the sales data was ingested into a MySQL database for efficient storage and querying.
   - **Schema Design:** The database schema was carefully designed to facilitate easy access and relational integrity. Tables included detailed records of sales transactions, customer information, product details, and other relevant data.
   - **Preliminary Analysis:** Basic SQL queries were executed to understand the data distribution, identify key metrics, and detect any anomalies or patterns. This phase involved calculating aggregates, understanding data distributions, and exploring relationships between different variables.

2. **Data Cleaning and Pre-processing with Power BI:**
   - **Database Connection:** The MySQL database was connected to Power BI, enabling seamless data import for further processing.
   - **Data Cleaning:** Within Power BI, several steps were undertaken to clean the data. This included handling missing values, removing duplicates, correcting inconsistencies, and transforming data into a usable format.
   - **Data Transformation:** The data was further processed to derive new metrics and dimensions, such as calculating sales performance over different periods, segmenting customers based on their purchasing behavior, and standardizing product categories.

#### Reporting and Dashboard Creation
- **Interactive Dashboard:** A comprehensive and interactive dashboard was developed in Power BI. The dashboard includes various visualizations such as bar charts, line graphs, pie charts, and geographic maps to provide a holistic view of sales performance.
- **Key Performance Indicators (KPIs):** Critical KPIs like total sales, sales growth, average order value, and customer lifetime value were prominently featured to track performance against targets.
- **Drill-down Capabilities:** The dashboard allows users to drill down into specific details, such as viewing sales by region, product category, and sales channels, enabling deeper insights into the data.
- **Dynamic Filters:** Users can apply dynamic filters to interact with the data in real-time, allowing for customized views and more specific analysis based on different criteria such as time periods, geographical locations, and customer segments.

#### Outcomes
- **Improved Decision-Making:** The insights derived from the dashboard enabled stakeholders to make informed decisions based on real-time data. Trends and patterns were easily identified, leading to better strategic planning.
- **Enhanced Data Accessibility:** By centralizing the data analysis process in Power BI, data was made more accessible to non-technical users, empowering a broader range of team members to engage with the data.
- **Actionable Insights:** The project successfully transformed raw sales data into actionable insights, identifying key drivers of sales performance and areas for improvement.

#### Tools and Technologies
- **MySQL:** Utilized for initial data exploration, storage, and preliminary analysis.
- **Power BI:** Used for data cleaning, transformation, and visualization, providing a robust platform for developing interactive dashboards and reports.

The "Sales_Insights" project exemplifies the integration of database management and data visualization tools to enhance business intelligence and support data-driven decision-making.



### Data Analysis Using SQL

1. Show all customer records

    `SELECT * FROM customers;`

1. Show total number of customers

    `SELECT count(*) FROM customers;`

1. Show transactions for Chennai market (market code for chennai is Mark001

    `SELECT * FROM transactions where market_code='Mark001';`

1. Show distrinct product codes that were sold in chennai

    `SELECT distinct product_code FROM transactions where market_code='Mark001';`

1. Show transactions where currency is US dollars

    `SELECT * from transactions where currency="USD"`

1. Show transactions in 2020 join by date table

    `SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;`

1. Show total revenue in year 2020,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";`
	
1. Show total revenue in year 2020, January Month,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`

1. Show total revenue in year 2020 in Chennai

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020
and transactions.market_code="Mark001";`


Data Analysis Using Power BI
============================

1. Formula to create norm_amount column

`= Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] ="USD#(cr)" then [sales_amount]*75 else [sales_amount], type any)`




