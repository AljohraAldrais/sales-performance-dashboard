# Dashboard Documentation

## Business Objective

The purpose of this dashboard is to provide a clear overview of sales performance and help users monitor key business metrics in one place.

The dashboard brings together sales, profit, cost, customer, product, store, and target information to support easier performance analysis.

## Business Requirements

The dashboard was designed to answer the following business questions:

- How are overall sales performing?
- How much profit is being generated?
- What is the current profit margin?
- How are sales performing across different regions?
- Which products generate the highest sales?
- Which customers generate the highest sales?
- How are sales and costs changing over time?
- What is the distribution of orders by status?
- How many customers and orders are being recorded each month?
- How does actual sales performance compare with the sales target?

## Key Performance Indicators

The dashboard includes the following main KPIs:

| KPI | Description |
|---|---|
| Total Sales | Total sales amount |
| Total Profit | Total profit generated |
| Profit Margin % | Profit as a percentage of sales |
| Total Cost | Total cost associated with sales |
| Total Quantity | Total quantity sold |
| Number of Customers | Distinct number of customers |
| Number of Orders | Distinct number of orders |
| Sales Target | Target sales amount |
| Sales Target Achievement % | Actual sales compared with the sales target |

## Dashboard Components

The dashboard provides several views for analyzing performance:

### Sales Performance

Monthly sales trends are used to identify changes in sales performance over time.

### Regional Performance

Sales and profit are compared across regions to identify stronger and weaker performing areas.

### Product Performance

The dashboard highlights the top-performing products based on sales.

### Customer Performance

The dashboard identifies the top customers based on their contribution to total sales.

### Cost Analysis

Monthly cost trends and sales-to-cost comparisons help provide visibility into cost performance.

### Order Analysis

Order status distribution provides an overview of the current order mix.

### Customer & Order Trends

Monthly customer and order trends provide visibility into changes in customer activity and order volume.

### Target Performance

Actual sales are compared with the defined sales target to measure target achievement.

## Filters

The dashboard provides interactive filters that allow users to analyze the data based on:

- Region
- Order Status
- Product
- Customer
- Date

These filters allow users to focus on specific areas of the business without changing the underlying data.

## Data Sources

The dashboard uses Excel-based datasets containing sales and supporting business information.

The data model combines transactional data with supporting dimensions for customers, products, categories, stores, suppliers, inventory, dates, and targets.

## Data Preparation

Power Query was used to prepare and transform the data before loading it into the Power BI data model.

The preparation process included:

- Reviewing the source data
- Cleaning and organizing columns
- Preparing data types
- Structuring the datasets for analysis
- Preparing the data for relationships and reporting

## Data Modeling

The Power BI model uses related tables to support analysis across different business dimensions.

The `Sales` table acts as the main transactional table, while supporting tables provide information about customers, products, categories, stores, dates, inventory, suppliers, and targets.

More details about the model and relationships are documented in the Data Model section of this repository.

## DAX

DAX measures were created to calculate the main business KPIs and analytical metrics used throughout the dashboard.

The documented measures include:

- Total Sales
- Total Profit
- Total Cost
- Profit Margin %
- Total Quantity
- Number of Customers
- Number of Orders
- Profit Target
- Sales Target
- Sales Target Achievement %

The complete DAX documentation is available in:

`DAX/measures.md`

## Tools & Technologies

- Power BI
- Power Query
- DAX
- Data Modeling
- Excel
- GitHub

## Project Outcome

The final dashboard provides an interactive view of sales performance and allows users to analyze key business metrics from multiple perspectives.

The project demonstrates practical experience in data preparation, data modeling, DAX calculations, dashboard design, and business-focused data visualization.
