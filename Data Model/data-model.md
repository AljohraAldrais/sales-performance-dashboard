# Data Model

## Overview

The Sales Performance Dashboard uses a relational data model designed to support sales, profitability, inventory, customer, product, store, supplier, and target analysis.

The model follows a dimensional structure where the `Sales` table acts as the primary transaction table, while supporting tables provide descriptive and analytical dimensions.

## Data Model Structure

The main tables in the model are:

- Sales
- Customers
- Products
- Categories
- Inventory
- Stores
- Suppliers
- ProductSupplier
- Date
- Month
- Targets

## Relationships

### Sales

The `Sales` table is the main transactional table and is connected to:

- `Date` using `Date`
- `Products` using `ProductID`
- `Customers` using `CustomerID`
- `Stores` using `StoreID`

These relationships allow sales to be analyzed by date, product, customer, and store.

### Inventory

The `Inventory` table contains inventory and stock-level information and is connected to:

- `Date` using the inventory date
- `Products` using `ProductID`
- `Stores` using `StoreID`

This allows inventory levels and stock status to be analyzed over time and across products and stores.

### Products

The `Products` table contains product information and is connected to:

- `Categories` using `CategoryID`
- `Sales` using `ProductID`
- `Inventory` using `ProductID`
- `ProductSupplier` using `ProductID`

### Categories

The `Categories` table provides product category information.

- `Categories → Products`
- Relationship key: `CategoryID`
- Cardinality: One-to-Many

### Customers

The `Customers` table contains customer information and is connected to:

- `Sales` using `CustomerID`
- Cardinality: One-to-Many

This relationship supports customer-level sales analysis.

### Stores

The `Stores` table contains store and regional information and is connected to:

- `Sales` using `StoreID`
- `Inventory` using `StoreID`
- `Targets` using `StoreID`

This enables analysis by store, city, and region.

### Suppliers

The `Suppliers` table contains supplier information and is connected to:

- `ProductSupplier` using `SupplierID`
- Cardinality: One-to-Many

### ProductSupplier

The `ProductSupplier` table acts as a bridge between products and suppliers.

It contains:

- `ProductID`
- `SupplierID`

This structure supports the relationship between products and their suppliers.

### Date

The `Date` table is the main date dimension used for time-based analysis.

It contains attributes such as:

- Date
- Day Name
- Is Weekend
- Month Name
- Month Number
- Month Start Date
- Quarter
- Year

The `Date` table is used to analyze sales and inventory trends over time.

### Month

The `Month` table provides monthly-level information used for monthly analysis and target alignment.

It contains:

- Month Name
- Month Number
- Month Start Date
- Year

### Targets

The `Targets` table contains sales and profit targets by month and store.

It includes:

- Month
- Month Number
- Profit Target
- Sales Target
- StoreID
- Target Month Start

The table is used to compare actual sales performance against predefined targets.

## Relationship Summary

| From | To | Key | Cardinality |
|---|---|---|---|
| Date | Sales | Date | One-to-Many |
| Date | Inventory | Date | One-to-Many |
| Month | Date | Month / Month Start | One-to-Many |
| Month | Targets | Month Start | One-to-Many |
| Products | Sales | ProductID | One-to-Many |
| Products | Inventory | ProductID | One-to-Many |
| Categories | Products | CategoryID | One-to-Many |
| Customers | Sales | CustomerID | One-to-Many |
| Stores | Sales | StoreID | One-to-Many |
| Stores | Inventory | StoreID | One-to-Many |
| Stores | Targets | StoreID | One-to-Many |
| Suppliers | ProductSupplier | SupplierID | One-to-Many |
| Products | ProductSupplier | ProductID | One-to-Many |

## Modeling Approach

The model separates transactional data from descriptive dimensions to improve analytical clarity and dashboard performance.

The structure enables users to analyze:

- Sales performance
- Profitability
- Costs
- Customer performance
- Product performance
- Inventory levels
- Store and regional performance
- Supplier relationships
- Target achievement

The model is designed to support interactive Power BI reporting through shared dimensions and consistent filtering across the dashboard.
